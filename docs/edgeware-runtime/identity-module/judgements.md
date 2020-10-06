# Judgements

### Judgements

After a user injects their information on chain, they can request judgement from a registrar. Users declare a maximum fee that they are willing to pay for judgement, and registrars whose fee is below that amount can provide a judgement.

When a registrar provides judgement, they can select up to six levels of confidence in their attestation:

* Unknown: The default value, no judgement made yet.
* Reasonable: The data appears reasonable, but no in-depth checks \(e.g. formal KYC process\) were performed.
* Known Good: The registrar has certified that the information is correct.
* Out of Date: The information used to be good, but is now out of date.
* Low Quality: The information is low quality or imprecise, but can be fixed with an update.
* Erroneous: The information is erroneous and may indicate malicious intent.

A seventh state, "fee paid", is for when a user has requested judgement and it is in progress. Information that is in this state or "erroneous" is "sticky" and cannot be modified; it can only be removed by complete removal of the identity.

Registrars gain trust by performing proper due diligence and would presumably be replaced for issuing faulty judgements.

To be judged after submitting your identity information, go to the ["Extrinsics UI"](https://polkadot.js.org/apps/#/extrinsics) and select the `identity` pallet, then `requestJudgement`. For the `reg_index` put the index of the registrar you want to be judged by, and for the `max_fee` put the maximum you're willing to pay for these confirmations.

If you don't know which registrar to pick, first check the available registrars by going to ["Chain State UI"](https://wiki.polkadot.network/docs/en/learn-identity) and selecting `identity.registrars()` to get the full list.

![Showing all registrars](https://wiki.polkadot.network/img/identity/14.jpg)

The image above reveals two registrars:

* Registrar 0, FcxNWVy5RESDsErjwyZmPCW6Z8Y3fbfLzmou34YZTrbcraL charges 25 KSM per judgement
* Registrar 1, Fom9M5W6Kck1hNAiE2mDcZ67auUCiNTzLBUdQy4QnxHSxdn charges 5 KSM per judgement

To find out how to contact the registrar after the application for judgement or to learn who they are, we can check their identity by adding them to our Address Book. Their identity will be automatically loaded.

![Gav is a registrar](https://wiki.polkadot.network/img/identity/15.jpg)

Gavin Wood is registrar \#0.

![Chevdor is registrar \#1](https://wiki.polkadot.network/img/identity/16.jpg)

Chevdor is registrar \#1. We pick that one.

![Requesting judgement](https://wiki.polkadot.network/img/identity/08.jpg)

This will make your identity go from unjudged:

![An unjudged identity](https://wiki.polkadot.network/img/identity/07.jpg)

To "waiting":

![A pending identity](https://wiki.polkadot.network/img/identity/09.jpg)

At this point, direct contact with the registrar is required - the contact info is in their identity as shown above. Each registrar will have their own set of procedures to verify your identity and values, and only once you've satisfied their requirements will the process continue.

Once the registrar has confirmed the identity, a green checkmark should appear next to your account name with the appropriate confidence level:

![A confirmed identity](https://wiki.polkadot.network/img/identity/10.jpg)

_Note that changing even a single field's value after you've been verified will un-verify your account and you will need to start the judgement process anew. However, you can still change fields while the judgement is going on - it's up to the registrar to keep an eye on the changes._

