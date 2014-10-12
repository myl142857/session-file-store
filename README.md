session-file-store
==================

Session file store is a provision for storing session data in the session file

> Note: session-file-store only supports express `>= 4.0.0`

## Installation

      $ npm install session-file-store

## Options

  - `path`       The directory where the session files will be stored. Defaults to `./sessions`
  - `ttl`        Time to live in seconds
  - `retries`    The number of retries to get session data from a session file. Defaults to 5
  - `factor`     Defaults to 1
  - `minTimeout` Defaults to 50
  - `maxTimeout` Defaults to 50

## Usage

Due to express `>= 4` changes, we need to pass `express-session` to the function `session-file-store` exports in order to extend `session.Store`:

    var session = require('express-session');
    var FileStore = require('session-file-store')(session);

    app.use(session({
        store: new FileStore(options),
        secret: 'keyboard cat'
    }));
