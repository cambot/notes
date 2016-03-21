# PyEphem

Libraries to check out:
- Collections
- argparse
- csv

# Flasky Goodness

Django: {tools & utils, web processes, worker processes}
- Components tend to get tightly coupled together
- introduces bottlenecks
- itteration difficult

Developers -> API -> DB front end

## Build for Services
- documentations & contracts become crucial
- composability

Django: take away the ORM and you aren't left with much.

## Flask: good for API's.
- explicit & passable app objects
- ORM's not required
- fewer batteries included -> more flexibility
- config is just a dictionary
- difficult to build monolithic apps, which can be a good thing.



# Porting Python
- nathan at event bright

## Why?
- dict compressions
- keyword only args
- Strings are Unicode

## Strategy: 
Dependencies, test, code data
Eventbright has 125 external depenencies. (full dependency graph)

## Tools
tools: 2to3, modernizer
~2900 broken tests

http://yergler.net/2013/evb3

# API's for mobile networks
Chris Ridenour
LISNR

REST is fine, but doesn't really make sense for mobile.
Goal: decrease the cost of latency.

## Easy Wins
- be fast at everything. (reads should always be cached)
- don't make me wait (writes should always go to celery)
- avoid sending bad data (make client validate everything first)
- stay in control (work with third party API's on your server, not though the mobile client)

## Stratigies to minimize latency
- global dump your data (JSON or whatever)
  -pros: ?
  -cons: bandwidth limited, read-only
  -experience: easy win, but not a long term solution
- HTTP Pipelining (v1.1)
  -pros: requests sent w/o responses
  -cons: responses must be in same order, proxies can mess up order most python servers don't support
  -experience: python manage.py run_gunicorn -k gevent_pysgi, not there right now. "HTTP 1.1 compliant" doesn't always mean support for pipelining exists.
- websockets
  -pros: starts as http request, supports https/SSL encryption
  -cons: not rest, requires your own protocol, should be on an event based server
  -experience: went with Tornado

http://wamp.ws
- provides asynch RPC & PubSub over websocket
- http-like endpoints, but really just structured msgs

Libraries
- Tornado
- Autobahn (WAMP) -- the also provide mobile libraries

# Better Mapping with Shapely
Alison Alvarez, Rhiza Labs

http://toblerity.github.io/shapely/manual.html
pip install shapely

geospacial databases are good for "in region" not so much for intersections or unions.

wkt: well-known-text.

shapely lets you tell how much one shape falls within another and handles holes really well.
Rhiza stack: Geo-db => Logic layer => JSON => Mapbox (& Mapnik and OpenStreetMaps)

## Using Shapely
- point + buffer
- joining/union shapes
  - need to be careful of gaps

DMA: Designated Market Area

weighted aggregation
- breaking zip code down to census groups
uses shapely to do computations.  Json/javascript does the rendering.

# Lightning Talks
## More regional stuff!
- what you need {#1: location, #2: solicit talks, #3: publicize}

## Gears
https://github.com/gears/gears
compile and concatenate JS & CSS assets

## Interactive Debugging in any Python Web Project
Ron Duplain
Werkzeug

## Gittip
@whit537
https://www.gittip.com/for/contributers/

## Woven
http://woventheapp.com
@joeshaw

duplicate detection: 8x8 pixle -> center of mass
Cubism

github.com/litl

## EqPy
solving systems of equations

## What I did during julython
Brad Montgomery
Django-commen5

## Imagine
@imaginebenefit
imaginefreedom.org: goal ending child slavery worldwide


# Sprinting
`git grep "..."` - grep searches what's git versioned.

`git stash`   - stashes uncomitted changes on a temp stack
`git checkout -b`


    ci[char]  - "change in [character pair]"
    ca[char]  - "change around [char pair]"
    lesty juggler
    syntatic - with flake8
    git pull https://github.com/mitechie/Bookie.git develop
    make test  - full suite
    bin/nosetests --with-id -vx -s bookie/tests/[module]

# Pyton & Fuse
Zach Wick

Examples: GlusterFS, GmailFS, WikipediaFS, EncFS

## Fuse in practice
writing methods to make something that looks like a filesystem

"Filesystem Class" methods:
- Required: getattr
- optional: readlink, mknod, mkdir, unlink, rename, ...

"File Class" methods:
- open, create, read, wriote, fgetattr, flush, ...

requires local mount point within your filesystem.

fusermount -u [path]

## copy.com and FUSE
github.com/copy-app/copy-fuse
- runs on Raspbery pi

Beware of network latency issues for cloud storages.

This is just a translation layer.  Only impliment the ops you care about.

zach@zachwick.com

