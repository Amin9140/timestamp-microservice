# Timestamp Microservice

A small REST API that converts dates into Unix timestamps and UTC strings. Built with Node.js and Express 5 as part of the freeCodeCamp Back End Development and APIs certification.

## Features

- Accepts dates as text (for example `2015-12-25`) or as Unix timestamps in milliseconds (for example `1451001600000`)
- Returns the current time when no date is given
- Returns a clear error message for invalid dates

## API usage

### `GET /api/:date?`

| Request | Response |
|---|---|
| `/api/2015-12-25` | `{"unix":1451001600000,"utc":"Fri, 25 Dec 2015 00:00:00 GMT"}` |
| `/api/1451001600000` | `{"unix":1451001600000,"utc":"Fri, 25 Dec 2015 00:00:00 GMT"}` |
| `/api` | The current time, in the same format |
| `/api/banana` | `{"error":"Invalid Date"}` |

## How it works

The route checks three cases in order:

1. **No date given:** returns the current time.
2. **All digits:** converts the text to a number and treats it as a Unix timestamp in milliseconds.
3. **Anything else:** tries to read it as a date with `new Date()`.

If the result isn't a valid date, the API returns an error object instead.

## Tech stack

- Node.js
- Express 5
- CORS

## Running locally

```bash
git clone https://github.com/Amin9140/timestamp-microservice.git
cd timestamp-microservice
npm install
npm start
```

Then open `http://localhost:8000` in your browser.

## Credits

Project specification by [freeCodeCamp](https://www.freecodecamp.org/).
