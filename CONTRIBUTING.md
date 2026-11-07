# Contributing to Hookshot

Thanks for helping. Never send, attach or commit the game, its keys, or anything the build made from it
(`work/`, `image.bin`, generated code, shader caches, saves). The `.gitignore` already blocks most of it.

## Setup

```
pip install -r requirements.txt
```

The build itself is described in the [readme](readme.md#how-to-build); the layout and tools are in
[docs/development.md](docs/development.md).

## Tests without the game

The tests in `tests/` and a few in `nx2/` need no game and no GPU. CI runs them on Linux and Windows
(`.github/workflows/source-regressions.yml`). Run one from the repository root:

```
python -I -B tests/test_fps_rate.py
```

Some compile a C++ fragment and need `g++` or `clang++` (`--cxx g++`). Tests that need a built game
(`nx2/test_insn.py`, `nx2/test_leaf.py`, `nx2/test_dll.py`) are run by hand.

When you fix a bug, add a test that fails without the fix if the code can be checked without the game, and add it
to the workflow.

## Pull requests

- Keep one change per pull request, and say what you saw and how you checked it (graphics card, where in the game).
- Commit messages: a short summary line in the imperative, then the reason if it is not obvious.
- Do not mix reformatting with a fix.
- Report bugs with where you were in the game, your graphics card, the driver version and a screenshot or video.
