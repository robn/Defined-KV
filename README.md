[![Build Status](https://secure.travis-ci.org/robn/Defined-KV.png)](http://travis-ci.org/robn/Defined-KV)

# NAME

Defined::KV - Create a KV pair, but only if the value is defined

# SYNOPSIS

    use Defined::KV;
    use Test::More;

    my $foo;
    my $bar = 1;
    my $baz = 0;

    my %dict = (
      defined_kv(foo => $foo),
      defined_kv(bar => $bar),
      defined_kv(baz => $baz),
    );

    is_deeply(\%dict, { bar => 1, baz => 0 });

# DESCRIPTION

`Defined::KV` exports a single function, `defined_kv`. Call it with two arguments. If the second argument is defined, both are returned, otherwise nothing is returned.

This exists to replace this construct:

    (defined $v ? ($k => $v) : ())

with something less awkward and repetetive, namely:

    defined_kv($k => $v)

# SUPPORT

## Bugs / Feature Requests

Please report any bugs or feature requests through the issue tracker
at [https://github.com/robn/Defined-KV/issues](https://github.com/robn/Defined-KV/issues).
You will be notified automatically of any progress on your issue.

## Source Code

This is open source software. The code repository is available for
public review and contribution under the terms of the license.

[https://github.com/robn/Defined-KV](https://github.com/robn/Defined-KV)

    git clone https://github.com/robn/Defined-KV.git

# AUTHORS

- Rob N ★ <robn@robn.io>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2017 by Rob N ★

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
