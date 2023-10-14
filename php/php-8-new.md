# What's new in php 8.0

### The Nullsafe Operator
```php
<?php

class User
{
    public function profile(): ?Profile
    {
        return rand(0, 1) ? null : new Profile();
    }
}

class Profile
{
    public function employment(): string
    {
        return 'web developer';
    }
}

$user = new User();

// php 8.0
echo $user->profile()?->employment() ?? 'Not provided';

//php 7.4
if ($profile = $user->profile()) {
    echo $profile->employment();
} else {
    echo 'Not provided';
}
```

### Match Expressions
```php
<?php

class Conversation
{

}

$obj = new Conversation();

// php 8.0
$type = match (get_class($obj)) {
    'Conversation' => 'started_conversation',
    'Reply' => 'replied_to_conversation',
    'Comment' => 'comment_on_lesson'
};

//php 7.4
switch (get_class($obj)) {
    case 'Conversation':
        $type = 'started_conversation';
        break;
    case 'Reply':
        $type = 'replied_to_conversation';
        break;
    case 'Comment':
        $type = 'comment_on_lesson';
        break;
}

echo $type;
```

### Constructor Property Promotion
```php

class User
{
    public function __construct(protected string $name) {}
}

class Plan
{
    public function __construct(protected string $name = 'monthly') {}
}

class SignUp
{
    public function __construct(protected User $name, protected Plan $plan) {}
}

$user = new User('name');
$plan = new Plan('yearly');

$signup = new SignUp($user, $plan);

print_r($signup);
```

### $object::class
```php
<?php

class Conversation
{

}

$obj = new Conversation();

print_r($obj::class);
```

### Named Parameters
```php
<?php

class Invoice
{
    public function __construct(protected $name, protected $plan, protected $date, protected $time) {}
}

$obj = new Invoice(plan: 'get', name: 'test', time: microtime(true), date: '2022');

print_r($obj);
```

### New String Helpers
```php
<?php

$word = 'start_text-in the middle _end';

var_dump(str_starts_with($word, 'start_'));
var_dump(str_ends_with($word, '_end'));
var_dump(str_contains($word, '-in'));

var_dump(str_starts_with($word, 'one_'));
var_dump(str_ends_with($word, '_two'));
var_dump(str_contains($word, 'several'));
```

### ??=
```php
<?php

// new
$count ??= 0;

// old
if (!isset($count))
    $count = 0;

print_r($count);
echo PHP_EOL;
```