# voice

how the words sound. like the look, the voice is chosen per project, in the [brief](brief.md), before any copy gets written. a devtool, a personal site and a product for a company shouldn't all talk the same way.

## constants

these hold in every voice.

- **it has to be readable.** a page starts by saying what it's for in a sentence, then shows the smallest thing that works, then the details. tables and short lists where something really is a list.
- **shorter by saying less,** not by chopping sentences into fragments.
- **every fact stays exact.** a voice changes the wording, never the content.
- **no slop.** no throat-clearing, no fake contrast ("not x. y."), no manufactured drama, no buzzwords, no em dashes, no emoji, no summary of what was just said.
- **a voice is studied, not themed.** collect real samples of it first (things a real person actually wrote), note what makes them work, and write from those. naming a voice and then writing the internet's average of it produces a costume. see the failure mode in [discord](voices/discord.md) for what that looks like.

## voices

every voice has a file in [voices/](voices/) with real samples, what it is, how it goes wrong and what it never does.

- **[discord](voices/discord.md)**: how i type. first person, lowercase, run-on, honest, a bit goofy. fits anything that's personally mine: my projects' docs and readmes, my site.

that's the only one written down so far. a project can pick it, or bring a different voice that suits it better, written up the same way: samples first.

## adding one

make `voices/<name>.md` in the shape of [discord](voices/discord.md): what it is, calibration samples from a real source, the failure mode with wrong and right pairs, a never list, and where it shipped. then add a line to the list above.
