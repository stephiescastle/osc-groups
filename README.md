# OscGroups

This repo contains a compiled version of http://www.rossbencina.com/code/oscgroups, written by Ross Bencina.

## Connecting to the server

Run `OscGroupClient` to connect to the server.

```bash
OscGroupClient {server} 22242 22243 22244 22245 {you} {yourpass} {group} {grouppass}
```

| Variable      | Description               |
| :------------ | :------------------------ |
| `{server}`    | url of the host server    |
| `{you}`       | your username (arbitrary) |
| `{yourpass}`  | yourpassword (arbitrary)  |
| `{group}`     | group you want to join    |
| `{grouppass}` | password for the group    |

## Using OSC messages in Max/MSP

1. Open a max patch that uses `udpsend 127.0.0.1 22244` and `udpreceive 22245`.

2. Concatenate and prepend your messages with your alias using `pak /alias`

   > This alias does not need to match your OscGroupClient username, but makes setup easier if it matches (so everyone knows what your nickname is and what to route by)

3. Use `route` to route messages from other users. Example `route /user1`

You can use the test patch as basis: [OSC-Groups-2021.maxpat](OSC-Groups-2021.maxpat)
