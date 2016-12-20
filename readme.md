# git-diff-img

![Example difference after replacing the left hand side with the right](doc/spot-the-diff-montage.png)
<sub><sup>The result of `git-diff-img`. Sample image by
[Muband](https://ja.wikipedia.org/wiki/%E5%88%A9%E7%94%A8%E8%80%85:Muband) from
the [Spot the difference](https://en.wikipedia.org/wiki/Spot_the_difference)
Wikipedia article; distributed under a CC BY-SA 3.0 license</sup></sub>

## Installation

### System Prerequisites
Install ImageMagick: `sudo apt install imagemagick`

### As a Git configuration (recommended)
```bash
git config --global difftool.diff-img.cmd 'compare "$LOCAL" "$REMOTE" png:- | montage -mode concatenate "$LOCAL" png:- "$REMOTE" png:- | display -title "$BASE: Local | Diff | Remote" png:-' &&
git config --global diff.guitool diff-img &&
git config --global alias.diff-img 'difftool -g'
```

### As an executable
1. [Download](https://raw.githubusercontent.com/niedzielski/git-diff-img/master/git-diff-img) git-diff-img
2. Mark git-diff-img executable: `chmod +x git-diff-img`
3. Move git-diff-img to *either* `~/bin` or `/usr/local/bin`: `mv git-diff-img ~/bin/` OR `mv git-diff-img /usr/local/bin/`
4. Verify git-diff-img is in your PATH: `which git-diff-img || echo "git-diff-img not found in PATH environment variable \"$PATH\""`

## Usage
Execute against images only: `git diff-img **.png`

## Links

- [diff-so-fancy](https://github.com/so-fancy/diff-so-fancy)
- [Improved Colored Diff](https://github.com/jeffkaufman/icdiff)

## License (Public Domain)
All code is public domain and may be used without limitation