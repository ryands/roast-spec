# roast-spec
Specification for logging and publishing coffee roasts

**Current Version:** 0 (initial draft is a work-in-progress)

## Summary

This is a specification for home (and possibly commercial?) coffee roasters to use when documenting their roasts.
The goal is to provide a common format for logging, sharing, and analyzing roast notes between likeminded independent
coffee roasters.

## Specification

Note: in future revisions this may be moved to another file, possibly [SPECIFICATION.md].

### File type and format

This specification is intended to be used with any file format that can be serialized into a hash.  It is recommended that the
format support arrays, strings, integers/numbers.  Examples and discussion will focus on yaml, json, and toml formats.

### The file

`example.yml`: An example roast

#### version: (`string`) [required]

Version must be present.  It can be a bare integer, but parsers should be able to handle a string value here.  There may be a
need to have a "2.1" in the event that a popular version that is not the latest needs something added/backported to it.

#### date: (`string`) [required]

Every roast must have a date provided.  Date format is expected to be in ISO 8601 format. Precision to minutes.

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

#### bean: (`object`) [required]

The bean being roasted.

```yaml
bean:
  country: Ethiopia
  region: Yirgacheffe
  farm: Some Farm
  lot: A
  varietal: (optional)
  vendor: Sweet Marias
  vendor_url: https://www.sweetmarias.com (optional)
  bean_url: https://www.sweetmarias.com/product/ethiopia-yirgacheffe-example-bean (optional)
  vendor_description: "Boy is it coffee" (optional)
```

#### weight: (`object`) [required]

The pre and post roast weight of the beans expressed in a float, combined with units.

#### environment (`object`) [optional]

```toml
Ambient temperature, humdity, and barometric pressure of roasting environment
expressed in a float.

todo:
Units will be standardized and defined globally.

[environment]
	temperature = 68.0
	humidity    = 40.0
	pressure    = 101.3
```
#### events: (`array<event>`) [optional]

#### notes: (`string`) [optional]

Any notes or commentary on the roast.

