# Cat Herd's Crook: Enforcing Standards in 10 Languages

## Intro
MongoDB drivers: how to talk to MongoDB in different languages, at different levels
	- Application API
	- TCP communication to MongoDB server

10 languages (and sync, async, legacy versions) each have different drivers, PLUS 3rd party drivers and share almost 0 code

Differences: not bugs, but reasonable choices that made unintentional differences that aren't necessarily known.

*Example*: You have a driver, and 2x MongoDB servers (a replica set for balancing)
We want to implemement: 'roundtrip threshold'
	- Measures how long it takes to each server
	- Only talk to servers that take minimum + 15ms round trip

Misinterpetation:
	1. Only hit best latency or server's <= 15ms round trip

Customer: "I expected load balancing but instead the nearest server just got slammed." Uh oh.

### Why???
- Too hard to review every implementation of the spec
- No authority

### False starts
- Write the feature spec really, really clearly `[Nope]`
- References implementation `[Nope]`
- Write tests in english `[Nope]`
- Cucumber (BDD, automated testing) `[Nope]`
	^Nobody wanted to write it

## Then came the dawn
YAML.
YAML = ~~Yet Another~~YAML Ain't Markup Language
- Lightweight config language, pretty simple
- Most languages can parse, plus YAML -> JSON
- Compared to JSON: more human readable
- Compared to Cucumber: language-neutral

### Why YAML?
- Standard comment format
- "Programmatic": DRY

### Test specs in YAML
- One set of tests used by all drivers
- Drivers must write a harness for YAML test suite; a script that parses the YAML tests and executes them
- Each spec becomes a new 'mini-language' but shared across all drivers

Unit tests: test small bits of functionality
- Able to support test-driven development
- Clearly describe elementary behavior

Integration tests

### These specs have bestowed upon us...
- Better Communication
- Better implementations (certainly more testable)
- More accountability and easier to enforce
- Encourages future specs to be written
- Standardizing own drivers, encouraging 3rd party drivers to follow suit
- We can prove that external drivers are trustworthy



