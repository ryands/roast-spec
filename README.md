# roast-spec
Specification for logging and publishing coffee roasts

**Current Version:** 0

## Summary

This is a specification for home (and possibly commercial?) coffee roasters to use when documenting their roasts.
The goal is to provide a common format for logging, sharing, and analyzing roast notes between likeminded independent
coffee roasters.

## Specification

Note: in future revisions this may be moved to another file, possibly [SPECIFICATION.md].

### File type and format

This specification is intended to be used with any file format that can be serialized into a hash.  It is recommended that the
format support arrays, strings, integers/numbers.  Examples and discussion will focus on yaml and json formats.

### The file

`example.yml`: An example roast

#### version: (`string`) [required]

Version must be present.  It can be a bare integer, but parsers should be able to handle a string value here.  There may be a
need to have a "2.1" in the event that a popular version that is not the latest needs something added/backported to it.

#### date: (`string`) [required]

Every roast must have a date provided.  Date format is expected to be YYYY-MM-DD (ex: 2017-07-22).

#### roaster: (`object`) [optional]

TODO: Document.

```yaml
roaster:
  type: Behmor 1600+
  timer: 20:30
  parameters: P1, A
```

#### duration: (`string`) [optional]

Total time of roasting.

#### bean: (`string`) [required]

The bean being roasted.  ex: Ethiopia Yirgacheffe Super Cool Farm Lot B

####  events: (`array<event>`) [optional]

#### notes: (`string`) [optional]

Any notes or commentary on the roast.



