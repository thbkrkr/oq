# oq

Command line tools to produce and consume data in the OVH Paas Queue.

## Install

```
curl https://github.com/thbkrkr/oq/releases/download/0.1/oq > /usr/local/bin/oq \
  && chmod +x /usr/local/bin/oq
```

## Getting started

`oq` needs 3 arguments: `-b <broker> -k <key> -t <topic>`.

### Consume

To consume, just start oq:
```
oq -b <region>.queue.ovh.net:9092  -k abcddefgh-0I9H8G7F6E5D4C3B2A1 -t myprefix.mytopic
```

### Produce

To produce, pipe your data in oq:
```
echo '{"date": "$(date %s)", "message": "'$RANDOM'"}' | \
  oq -b <region>.queue.ovh.net:9092  -k abcddefgh-0I9H8G7F6E5D4C3B2A1 -t myprefix.mytopic
```

## Example

![Example](/images/example.png)