The basic setup for minimanta was both simple and undocumented.

1) Make a config.json file that looks an awful lot like the config.json.dist.

Common changes include choosing a different root directory and port.

2) Front end this service with something doing ssl termination.  I use haproxy.

3) Put public keys in the right places for each user.

Authentication, like in manta, operates on ssh key signed messages.
Unlike in manta, there's no Triton SDC to reference here.

The keys that sign the message need to be in `~~/keys/<fingerprint>` in manta 
terms.  In local filesystem terms, that's the 
`<root directory from config.json>/<username>/keys/<fingerprint>` 
file.

The filename should be the fingerprint of the key, and contain the full ssh 
public key.


