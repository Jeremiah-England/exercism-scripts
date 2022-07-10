# Exercism Scripts

See https://exercism.org/docs/using/solving-exercises/working-locally for the
real exercism CLI.

## `exercism-get`

When I worked on exercism problems, I wanted to download them each to a git
repository so I can see diffs and stuff of the original files. The
`exercism-get` script does that. For example:

```sh
exercism-get plsql/hello-world
```

This will download the `hello-world` lesson from the `plsql` track to your
exercism workspace directory (`$(exercism workspace)/plsql/hello-world`). Then
it will make the exercise directory a git repository and commit the initial
files.

## `exercism-search`

Another script here is the `exercism-search` script. It just allows you to
search all the exercism exercises. For example, if you wanted to know what
exercises were in the plsql track, you could do this.

```sh
exercism-search plsql/
# plsql/hello-world
# plsql/binary
# plsql/difference-of-squares
# plsql/gigasecond
# plsql/grains
# plsql/hamming
# plsql/leap
# plsql/nth-prime
# plsql/raindrops
# plsql/rna-transcription
# plsql/roman-numerals
```

But before that works, you will need to run `exercism-search --refresh`. That
just downloads all the exercise names to some files in `~/.cache/exercism/`.
Since it is all cached, you do not need to hit the network to search normally.
That makes it very fast.

## Issue

One interesting workflow that I had in mind while creating these scripts was
starting off a new course by downloading all the exercises for it. You could do
this with:

```sh
exercism-search plsql/ | xargs --max-args 1 exercism-get
```

Unfortunately, that does not work. You get an error with "Error: You have not
unlocked this exercise" right after the `plsql/hello-world` lesson is
downloaded, and the script stops.
