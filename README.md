# mc-leveldb-rs

This was originally a fork that provided an implementation of LevelDB which could handle Mojang's modified format (which used ZLib instead for compression), but it's now obsolete. **`leveldb-rs` has now worked that support into the original repo (better than the way I did it), so that one is now perferable since it's actually maintained.**

Basically, this fork is *deprecated*. I don't think anyone used it, so I don't think anyone cares.

Original README from the original project follows.

<hr>

# leveldb-rs

[![crates.io](https://img.shields.io/crates/v/rusty-leveldb.svg)](https://crates.io/crates/rusty-leveldb)
[![Travis
CI](https://api.travis-ci.org/dermesser/leveldb-rs.svg?branch=master)](https://travis-ci.org/dermesser/leveldb-rs)

A fully compatible implementation of LevelDB in Rust. (any incompatibility is a
bug!)

The implementation is very close to the original; often, you can see the same
algorithm translated 1:1, and class (struct) and method names are similar or
the same.

**NOTE: I do not endorse using this library for any data that you care about.**
I do care, however, about bug reports.

## Status

Working well, with a few rare bugs (see issues).

## Goals

Some of the goals of this implementation are

* As few copies of data as possible; most of the time, slices of bytes (`&[u8]`)
  are used. Owned memory is represented as `Vec<u8>` (and then possibly borrowed
  as slice). Zero-copy is not always possible, though, and sometimes simplicity is favored.
* Correctness -- self-checking implementation, good test coverage, etc. Just
  like the original implementation.
* Clarity; commented code, clear structure (hopefully doing a better job than
  the original implementation).
* Coming close-ish to the original implementation; clarifying the translation of
  typical C++ constructs to Rust, and doing a better job at helping understand the internals.
