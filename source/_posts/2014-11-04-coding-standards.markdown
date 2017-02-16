---
layout: post
title: "Coding Standards"
date: 2014-11-04 22:59:51 +0200
comments: true
categories: 
- Development Conventions
- Code Quality
---

Coding standard is important part of code quality. It's important as improves code readability, decrease code review time and helps found errors in code.

That's why such group as [FIG](http://www.php-fig.org/) exists. The idea behind the group is for project representatives to talk about the commonalities between our projects and find ways we can work together.

As most of projects use different coding standards currenly a lot of them are migrating to PRS-2.

<!--more-->

## Tools
 - [PHP CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) to check code agains rulesets
 - [PHP CS Fixer](https://github.com/fabpot/PHP-CS-Fixer) to automate fixing of standards issues (PSR-1 and PSR-2 compatible)

## PHP CodeSniffer

### Installation

To install phpcs via pear

```
pear install PHP_CodeSniffer
```

### Configuration

To set prefered coding standard

```
phpcs --config-set default_standard PSR2
```

Check for installed coding standards

```
phpcs -i
```

Coding standards location

```
pear config-show | grep php_dir
ls -la /path/to/pear/PHP/CodeSniffer/Standards/PSR2
```

Setting the installed standard paths

```
$ phpcs --config-set installed_paths /path/to/one,/path/to/two
```

Hiding warnings by default

```
phpcs --config-set show_warnings 0
```

## PHP CS Fixer

There are good documentation at [Sensiolab site](http://cs.sensiolabs.org/).

For vim I use [vim plugin](https://github.com/stephpy/vim-php-cs-fixer).

```
let g:php_cs_fixer_path = "~/Bin/php-cs-fixer.phar"
Bundle 'stephpy/vim-php-cs-fixer'
nnoremap <silent><leader>f :call PhpCsFixerFixFile()<CR>e:<CR>
```

## Coding Standards customization

As there are a lot of legasy code and it's hard change all codebase in one moment to PSR-2 you can modify coding standards to your needs.

[My PSR-2 modified standard](https://github.com/ishenkoyv/PSR2IYV) includes changes to support php <5.3 projects (like Zend Framework 1.12), ignore errors for methods chaining etc.

[CodeSniffer Cheat Sheet](http://ianty.com/CodeSniffer_1.3.0.html) can be helpfull for modification coding standards to fit your needs.
