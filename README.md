
### Installation of Ruby and other requirements:
```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```
### Configuration of Ruby Gems (do not want to install them as root user)
```bash
echo '\n# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
### Install bundler
```shell
gem install jekyll bundler
```
### Running Jekyll-Based site
 You will want to run the command:
 ```shell
 bundle
 ```
 just to make sure that gems dependencies are installed and checked.

 To execute and serve (locally) a Jekyll site, run:
 ```shell
 bundle exec jekyll serve
 ```

 ### Notes:

 You may have to change the permissions of the directory you hold your repo in.
 If it looks like: `drwxrwxrwx 1 root 197609 0 Jun 18 22:23 {placeholder}.github.io/`, you will need to use `sudo chown -R $USER:$USER <filepath>`## Installation

[**Use this template**][use-template] to generate a brand new repository and name it `<GH_USERNAME>.github.io`, where `GH_USERNAME` represents your GitHub username.

Then clone it to your local machine and run:

```
$ bundle
```

## Usage

Please see the [theme's docs](https://github.com/cotes2020/jekyll-theme-chirpy#documentation).

## License

This work is published under [MIT][mit] License.

[gem]: https://rubygems.org/gems/jekyll-theme-chirpy
[chirpy]: https://github.com/cotes2020/jekyll-theme-chirpy/
[use-template]: https://github.com/cotes2020/chirpy-starter/generate
[CD]: https://en.wikipedia.org/wiki/Continuous_deployment
[mit]: https://github.com/cotes2020/chirpy-starter/blob/master/LICENSE
