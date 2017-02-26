# Revocation protocol
Decentralised protocol to keep the user safe and the Web platform powerful & healthy.

## Rationale
To encourage the proposal and implementation of powerful web APIs, an effective,
non-exploitable permission revocation scheme is needed so in case of detecting
harmful activities, the User Agent could protect the user against these abuses.

Read more in the [Web Computing](https://annevankesteren.nl/2016/07/web-computing)
and [Towards the Web of Trust](https://salvadelapuente.com/posts/2016/07/29/towards-the-web-of-trust/)
articles.

## Typical use case
I'm using a messages.com IM web app which use a propietary TCP protocol, so I
grant the application for using a hypothetical raw sockets API for the Web.

Suddenly, whitehackers.org discover that the application is being used to
scan local networks by implementing a CORS-free version of HTTP.

whitehackers.com uploads the evidence to the revocation decentralised database,
warning notices are spread through the system so other people can confirm the
evidence. Eventually, the UA consider there is enough information to declare
that piece of JavaScript as harmful and it revokes socket permission for the
app, warning the user about the potential risk of using this app.

It is still unclear if the user would have a chance to ignore the advice
about blocking the app or not.

## Design goals

### Decentralised
The Web should not be curated by a few so the system should avoid centralised
designs.

### Accessible
The design of such a network should allow any user to become a voter joining
the voting network.

### Factual
Judgement must be supported by confirmed evidence to become relevant. False
positives can seriously damage the image of a web property. Competitors should
not be able of running smear campaigns against each other.

### Deterrent
Both for web properties and voters, being marked as harmful or unreliable should
be hard to reverse so not only bad behaviour is discouraged but also emitting
intentional false positives is punished some way.

### Transparent
Every event related to a web property should be immediately reported to the
responsibles.

### Appealable
Evidence can be clarified by web property's owners.

### Ammendable
The complete system should be open for modification of the criteria governing
the system to adapt itself to the times.

### Open
And of course, it should remain open for the users to audit system behaviour.

---

Also, implementing the opt-in security mechanisms the platform offers right now
should decrease the chance of being marked as a pottential danger.

## On user capabilities
Once a web property is marked as harmfull, the UA should wanr the user but
what happen from here is up to the browser. In my opinion, the user should
remain in control, even if that implies shooting their own feet (situation
that the browser must minify and discourage but not forbid).

## To be defined
Former design goals don't speal about solutions but about the environmental
conditions of the ideal system. It is important to accurately define the meaning
of evidence, identity, web property, voter, evidence confirmation, feedback,
trustiness and other concepts.

## Next steps
As you can see, there is no specific design. My intention is to hold an open
discussion to search a viable solution for an MVP. I would bet for a
cross-compatible web extension for implementing a P2P database holding the
information. I suppose I will start to talk about it in my blog and send commits
to this repo.
