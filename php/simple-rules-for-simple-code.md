# Simple rules for simple code

## No abbreviation

<table>
<tr><td> Bad </td> <td> Good </td></tr>
<tr><td>

```php
<?php

class Trnsltr
{

}
```

</td><td>

```php
<?php

class Translator
{

}
```

</td></tr>

<tr><td>

```php
<?php

foreach ($x as $people) {

}
```

</td><td>

```php
<?php

foreach ($person as $people) {

}
```

</td></tr>

<tr><td>

```php
<?php

class UserRepository
{
    public function fetch($billingId)
    {
        
    }
}
```

</td><td>

```php
<?php

class UserRepository
{
    public function fetchByBillingId($id)
    {
        
    }
}
```

</td></tr>

<tr><td>

```php
<?php

class Order
{
    public function prepAndShipAndNotifyUser()
    {
        
    }
}
```

</td><td>

```php
<?php

class Order
{
    public function process()
    {
        
    }
}
```

</td></tr>

</table>

## Don't use else

<table>
<tr><td> Bad </td> <td> Good </td> <td> Very good </td></tr>
<tr><td>

```php
<?php

public function store()
{
    $input = Request::all();
    $validation = Validator::make($input, ['username' => 'required']);
    
    if (date('l') != 'Friday') {
        if ($validation->passes()) {
            Post::create($input);
            return Redirect::home();
        } else {
            return Redirect::back()->withInput()->withErrors($validation);
        } 
    } else {
        throw new Exception('We do not work on Friday!!!');
    }
}
```

</td><td>

```php
<?php

public function store()
{
    $input = Request::all();
    $validation = Validator::make($input, ['username' => 'required']);
    
    if (date('l') == 'Friday') {
        throw new Exception('We do not work on Friday!!!');
    } 
    if ($validation->failed()) {
        return Redirect::back()->withInput()->withErrors($validation);
    }
    
    Post::create($input);
    
    return Redirect::home();
}
```

</td><td>

```php
<?php

public function store()
{
    $input = Request::all();
    
    $this->validator->validate($input);
    
    Post::create($input);
    
    return Redirect::home();
}
```

</td></tr>


<tr><td>

```php
<?php

public function signup(subscription $subscription)
{
    if ($subscription) {
        $this->createmonthlysubscription();
    } else {
        $this->createforeversubscription();
    }
}
```

</td><td>

```php
<?php

public function signup(subscription $subscription)
{
    $subscription->create();
}

function getSubscription($type)
{
    if ($type == 'forever') {
        return new ForeverSubscription();
    }
    
    return new MonthlySubsctiprion();
}

signUp(getSubscription($type));
```

</td></tr>

</table>

## One level of indentation

<table>
<tr><td> Bad </td> <td> Good </td><tr>
<tr><td>

```php
<?php

class BankAccount
{
   protected $accounts;
   
   public function __construct($accounts) 
   {
        $this->accounts = $accounts;
   }
   
   public function filterBy($accountType)
   {
        $filtered = [];
        
        foreach($this->accounts as $account) {
            if ($account->type() == $accountType) {
                if ($account->isActive()) {
                    $filtered[] = $account;
                }
            }
        }
        
        return $filtered;
   }
}

class Account
{
    protected $type;
    
    public function __construct($type) 
    {
        $this->type = $type;
    }
    
    public static function open($type)
    {
        return new static($type);
    }
    
    public function type()
    {
        return $this->type;
    }
    
    public function isActive()
    {
        return true;
    }
}

$accounts = [
    Account::open('checking'),
    Account::open('saving'),
    Account::open('checking'),
    Account::open('savings'),
];

$accounts = new BankAccounts($accounts);
```

</td><td>

```php
<?php

class BankAccount
{
   protected $accounts;
   
   public function __construct($accounts) 
   {
        $this->accounts = $accounts;
   }
   
   public function filterBy($accountType)
   {
        return array_filter($this->account, function ($account) use ($accountType) {
            return $account->isOfType($accountType);
        });
   }
}

class Account
{
    protected $type;
    
    public function __construct($type) 
    {
        $this->type = $type;
    }
    
    public static function open($type)
    {
        return new static($type);
    }
    
    public function isOfType($accountType)
    {
        return $this->type() == $accountType && $this->isActive();
    }
    
    protected function type()
    {
        return $this->type;
    }
    
    protected function isActive()
    {
        return true;
    }
}

$accounts = [
    Account::open('checking'),
    Account::open('saving'),
    Account::open('checking'),
    Account::open('savings'),
];

$accounts = new BankAccounts($accounts);
```

</td></tr>

</table>

## Limit your instance variable

<table>
<tr><td> Bad </td> <td> Good </td><tr>
<tr><td>

```php
<?php

class UsersController
{
   protected $userService;
   protected $registrationService;
   protected $userRepository;
   protected $stripe;
   protected $mailer;
   protected $userEventRepository;
   protected $logger;
   
   public function __construct(
        UserService $userService,
        RegistrationService $registrationService,
        UserRepository $userRepository,
        Stripe $stripe,
        Mailer $mailer,
        UserEventRepository $userEventRepository,
        Logger $logger
   ) 
   {
   }
}
```

</td><td>

```php
<?php

class UsersController
{
   protected $userService;
   protected $mailer;
   protected $logger;
   
   public function __construct(UserService $userService) 
   {
   }
}
```

</td></tr>

</table>
