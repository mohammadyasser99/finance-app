https://github.com/mohammadyasser99/finance-app/assets/131922865/c8f7176b-cfc8-4ffc-9ffe-ca601f01e02b

## Getting started

To get started with the app, clone the repo and then install the needed gems. You can clone the repo as follows:

```
$ git clone git@github.com:mohammadyasser99/finance-app.git
$ cd finance-app
```

To install the gems, you will need the same versions of Ruby and Bundler used to build the sample app, which you can find using the `cat` and `tail` commands as follows:

```
$ cat .ruby-version
<Ruby version number>
$ tail -n1 Gemfile.lock
   <Bundler version number>
```

Next, install the versions of `ruby` and the `bundler` gem from the above commands. The Ruby installation is system-dependent; on the cloud IDE recommended in the tutorial, it can be installed as follows:

```
$ rvm get stable
$ rvm install <Ruby version number>
$ rvm --default use <Ruby version number>
```

```
$ gem install bundler -v <version number>
```

Then the rest of the necessary gems can be installed with `bundle` (taking care to skip any production gems in the development environment):

```
$ bundle _<version number>_ config set --local without 'production'
$ bundle _<version number>_ install
```

Here you should replace `<version number>` with the actual version number. For example, if `<version number>` is `2.3.14`, then the commands should look like this:

```
$ gem install bundler -v 2.3.14
$ bundle _2.3.14_ config set --local without 'production'
$ bundle _2.3.14_ install
```

If you run into any trouble, you can remove `Gemfile.lock` and rebundle at any time:

```
$ rm -f Gemfile.lock
$ bundle install
```

Next, migrate the database:

```
$ rails db:migrate
```

Finally, run the test suite to verify that everything is working correctly:

```
$ rails test
```

If the test suite passes, you’ll be ready to seed the database with sample users and run the app in a local server:

```
$ rails db:seed
$ rails server
```
