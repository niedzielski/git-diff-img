# git-diff-img

![Example difference after replacing the left hand side with the right](doc/spot-the-diff-montage.png)
<small>The result of `git diff-img`. Sample image by
[Muband](https://ja.wikipedia.org/wiki/%E5%88%A9%E7%94%A8%E8%80%85:Muband) from
the [Spot the difference](https://en.wikipedia.org/wiki/Spot_the_difference)
Wikipedia article; distributed under a CC BY-SA 3.0 license</small>

## Installation

### System Prerequisites
Install ImageMagick: `sudo apt install imagemagick`

### As a Git configuration (**recommended**)
```bash
git config --global alias.diff-img difftool\ -x\ \''compare -alpha copy "$LOCAL" "$REMOTE" png:- | montage -mode concatenate "$LOCAL" png:- "$REMOTE" png:- | display -title "$BASE: Local | Diff | Remote" png:-'\'
```

### As an executable (**not** recommended)
This is an *alternative* installation procedure that is unnecessary if the Git
configuration is used. It's not recommended because it requires an understanding
of PATH lookup

```bash
curl https://raw.githubusercontent.com/niedzielski/git-diff-img/master/git-diff-img -o ~/bin/git-diff-img &&
chmod +x ~/bin/git-diff-img
```

## Usage
Execute against images only: `git diff-img **.png`

## Links

- [diff-so-fancy](https://github.com/so-fancy/diff-so-fancy)
- [Improved Colored Diff](https://github.com/jeffkaufman/icdiff)

## License (Public Domain)
All code is public domain and may be used without limitation.
