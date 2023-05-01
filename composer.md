# Composer

## Search packages

1) Go to site: https://packagist.org/ or
2) Console command: `composer search <collection>`

## Here an example of `composer.json`

```json
{
  "name": "your-vendor-name/package-name",
  "description": "A short description of what your package does",
  "authors": [
    {
      "name": "Your Name",
      "email": "test@test.com"
    }
  ],
  "require": {
    "illuminate/collections": "^10.9"
  },
  "autoload": {
    "psr-4": {
      "Core\\": "Core/",
      "Http\\": "Http/"
    }
  },
  "require-dev": {
    "pestphp/pest": "^2.5"
  },
  "config": {
    "allow-plugins": {
      "pestphp/pest-plugin": true
    }
  }
}
```