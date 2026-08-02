# emblink-packages

The EmbLinkOS package registry. One directory per package holds its SIGNED
manifest (`.pkg`) and the EMBX bundle. The OS clones this over HTTPS (our own
git-over-HTTPS + TLS), then `pkg install`s a package -- verifying the manifest
signature against its trusted key on arrival. Trust is in the signature, not the
channel: a compromised host cannot inject a bad binary.
