# Exercism Scripts

See https://exercism.org/docs/using/solving-exercises/working-locally for the
real exercism CLI.

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
