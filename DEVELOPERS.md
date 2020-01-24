

## Installing the website for local development

```
git clone git@github.com:toronto-perl-mongers/toronto-perl-mongers.github.io.git

git submodule update --init --recursive
```

## Building the website

You need to install hugo in order to build the website

```
brew install hugo
```

Then to launch the website

```
hugo server
```

If you also want it to build local drafts, then use

```
hugo server --buildDrafts
```

## Viewing the website

Once you have launched the hugo dev server, you can view the website locally on the following URL:

```
http://localhost:1313
```
