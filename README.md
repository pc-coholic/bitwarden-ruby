*(Note: This is still a work in progress.
This project is not associated with the
[Bitwarden](https://bitwarden.com/)
project nor 8bit Solutions LLC.)*

## bitwarden-ruby

A small, self-contained API server written in Ruby to provide a
private backend for the open-source
[Bitwarden apps](https://github.com/bitwarden).

Data is stored in a local SQLite database.
This means you can easily run it locally and have your data never leave
your device, or run it on your own web server via Rack and some front-end
HTTP server with TLS to support logging in from multiple devices.
Backing up your data is as easy as copying the `db/production.sqlite3` file
somewhere.

### API Documentation

This project also contains independent
[documentation for Bitwarden's API](https://github.com/jcs/bitwarden-ruby/blob/master/API.md)
written as I work on this server, since there doesn't seem to be any
documentation available other than the
[.NET Bitwarden code](https://github.com/bitwarden/core)
itself.

## Usage

Run `bundle install` at least once.

To run via Rack on port 4567:

	env RAILS_ENV=production bundle exec rackup config.ru

You'll probably want to run it once with signups enabled, to allow yourself
to create an account:

	env RAILS_ENV=production ALLOW_SIGNUPS=1 bundle exec rackup config.ru

Run test suite:

	bundle exec rake test

### License

Copyright (c) 2017 joshua stein `<jcs@jcs.org>`

Permission to use, copy, modify, and distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.