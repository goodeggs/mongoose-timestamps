# goodeggs-mongoose-timestamps

Adds createdAt and updatedAt fields to any schema.

Uses `node-clock` internally so stubbing `clock.now` will determine time value used for model timestamps.

[![NPM version](http://img.shields.io/npm/v/goodeggs-mongoose-timestamps.svg?style=flat-square)](https://www.npmjs.org/package/goodeggs-mongoose-timestamps)
[![Build Status](http://img.shields.io/travis/goodeggs/goodeggs-mongoose-timestamps.svg?style=flat-square)](https://travis-ci.org/goodeggs/goodeggs-mongoose-timestamps)
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://github.com/goodeggs/goodeggs-mongoose-timestamps/blob/master/LICENSE.md)

## Usage

```
npm install goodeggs-mongoose-timestamps
```

```coffee
timestamps = require 'goodeggs-mongoose-timestamps'

schema = new mongoose.Schema {}
schema.plugin timestamps
```

By default, it creates indices for both attributes named `timestamps_created_at` and `timestamps_updated_at`. To override
this behavior:

```coffee
# Creates indices for both attributes by default
schema.plugin timestamps

# Does not create indices
schema.plugin timestamps, createIndices: false

# Only create updatedAt index, descending order
schema.plugin timestamps, createIndices: {updatedAt: -1}
```

## Contributing

Please follow our [Code of Conduct](https://github.com/goodeggs/goodeggs-mongoose-timestamps/blob/master/CODE_OF_CONDUCT.md)
when contributing to this project.

```
$ git clone https://github.com/goodeggs/goodeggs-mongoose-timestamps && cd goodeggs-mongoose-timestamps
$ npm install
$ npm test
```

_Module scaffold generated by [generator-goodeggs-npm](https://github.com/goodeggs/generator-goodeggs-npm)._
