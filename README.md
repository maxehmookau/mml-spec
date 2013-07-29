Music Markup Language (MML)
========

Some ideas of better expressing music as plain text than using Music XML or other proprietary technologies.

## Assumptions

> Rule No 1. We should make as few assumptions as possible. But, we have to make some.

1. Music has bars. These may be of an irregular size, however.
1. Bars conform to a time signature, however odd the time signature may be.
1. Written music is not constrained to western instruments and 'traditional' functional harmony.

## Syntax

> This is a draft document, it will change.

### Metadata

Each document may contain metadata. The metadata section may contain the following information as key-value pairs:

    title: Title
    author: Author Name
    ...

The metadata section may also contain default attributes that apply throughout the document:

    ...
    time: 4/4
    tempo: 4=150

These default values will be applied to all bars in the document except where the values have been overridden. (See Bars)

Here's an example metadata section of an MML document.

	# hungarian5.mml
    -
    title: Hungarian Dance No. 5
    author: Brahms
    time: 4/4
    tempo: 8=120
    -

### Bars

Each document contains many bars, each bar is defined using an opening and closing set of three dashes (---).

A bar will inherit the document time signature unless specified in square brackets after the dashes at the beginning of the bar, e.g. `--- {4/4}`