## Hi 👋
```php
<?php

namespace App\People;

/**
 * @requires PHP 8.4
 */
#[AsHuman]
final class OskarStark extends SymfonyCoreDeveloper implements DeveloperInterface, ManagerInterface
{
    use Symfony;
    use PostgreSQL;
    use Twig;
    use Ops;

    public const FIRSTNAME = 'Oskar';
    public const LASTNAME = 'Stark';
    
    public function __construct(
        public \DateTimeImmutable $birthDate = new \DateTimeImmutable('1985-02-20'),
        public string $email = 'oskarstark@googlemail.com',
        public string $company = 'SensioLabs Germany', // https://sensiolabs.com
        public string $placeOfResidence = 'Berlin, Germany',
    ) {
    }
    
    public function getTwitter(): ?SocialAccountInterface
    {
        return new TwitterAccount('https://twitter.com/oskarstark');
    }
    
    public function isOpenForFreelanceWork(): bool
    {
        return true;
    }
    
    /**
     * @return array<string, string>
     */
    public function getMaintainedGithubActions(): array
    {
        return [
           'PHPStan'      => 'https://github.com/OskarStark/phpstan-ga',
           'PHP-CS-Fixer' => 'https://github.com/OskarStark/php-cs-fixer-ga',
        ];
    }
}
```

