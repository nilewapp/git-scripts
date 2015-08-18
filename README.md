# Git-scripts

A set of git utilities.

## branch-per-commit

Create a branch for every commit between a base revision and HEAD.

Assume the following history exists:

    A---B---C---D HEAD

From this point, the result of the following command:

    git branch-per-commit A topic

would be:

    A---B topic-1
         \
          C topic-2
           \
            D topic-3 HEAD

## cherry-base

Like `rebase-all` but using `cherry-pick` instead of `rebase`.

## rebase-all

Rebases a series of branches on top of each other.

Assume the following history exists:

    A---B---C topic-1
         \
          D---E topic-2
           \
            F topic-3

From this point, the result of the following command:

    git rebase-all A topic-{1,2,3}

would be:

    A---B---C topic-1
             \
              D---E topic-2
                   \
                    F topic-3
