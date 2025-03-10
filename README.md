## Hi 👋
```php
<?php

namespace App\Developer;

/**
 * @requires PHP 8.4
 */
#[AsHuman]
final class OskarStark extends SymfonyCoreDeveloper implements DeveloperInterface
{
    use Symfony;
    use PostgreSQL;
    use Twig;
    use Ops;

    public const FIRST_NAME = 'Oskar';
    public const LAST_NAME = 'Stark';
    
    public function __construct(
        private \DateTimeImmutable $birthDate = new \DateTimeImmutable('1985-02-20'),
        private string $email = 'oskarstark@googlemail.com',
        private string $company = 'SensioLabs Germany', // https://sensiolabs.com
        private string $placeOfResidence = 'Berlin, Germany',
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

