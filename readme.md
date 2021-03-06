# Baapan

![](https://github.com/dpjayasekara/baapan/raw/master/docs/logo.png)

**Baapan brings the all of the NPM goodness right into your REPL. On-demand!!.**

> `baapan` only works on Node.js v10.x.x or above as it requires REPL to be started with `--experimental-repl-await` flag.

Using Node REPL for quick local testing is a common practice among JavaScript/Node developers. But the problem with the REPL is, you don't have the luxury to take advantage of the entire NPM ecosystem out-of-the-box. 

An alternative is, using something like RunKit. But fiddling with sensitive data in an online tool is not the best choice for many developers.

While using Node REPL, if you feel you need an NPM module to quickly test something (e.g, `lodash` to do some quick object/array manipulation, `uuid` to quickly generate some uuid), you'll have to manually install it via NPM and load it onto the REPL.

**Baapan** is a replacement for `require()` in node REPL. If the module you need is not installed locally, it will immediately grab it from NPM and load it to the console. Effortless! ✨😎!!

![](https://github.com/dpjayasekara/baapan/raw/master/docs/screenshot.png)

### How?

#### Step 1: Install baapan on your home directory

Navigate to your home directory, and run:

```sh
npm install baapan
```
#### Step 2: Load baapan with REPL

```sh
node --require baapan --experimental-repl-await
```
**Important!!** Baapan relies on `async-await` in REPL, therefore you need to enable the use of `async-await` in REPL using `--experimental-repl-await` flag.


#### Step 3: Use `await baapan()` instead of `require`

```
> const lodash = await baapan('lodash')
+ lodash@4.17.11
updated 1 package and audited 24204 packages in 2.501s
found 0 vulnerabilities

> lodash.concat([1], 2, [3,4])
[ 1, 2, 3, 4 ]
```

Baapan will immediately download the module via `npm` and `require` it so that it's available on the REPL!!!!

**You can also `require` a submodule with `baapan()`. See the following:**

![](https://github.com/dpjayasekara/baapan/raw/master/docs/uuid.png)

------------------

**If you feel lazy to type the entire command everytime you need to start the REPL, just go ahead and add an alias for the command in your `~/.bashrc` or `~/.bash_profile`.**

For `~/.bashrc`

```
$ echo "alias nodeb='node --require baapan --experimental-repl-await'" >> ~/.bashrc
$ source ~/.bashrc
```

For `~/.bash_profile`

```
$ echo "alias nodeb='node --require baapan --experimental-repl-await'" >> ~/. bash_profile
$ source ~/.bash_profile
```

**Feel free to drop any issues/feature requests/PRs at any time!!**

-----------------

<a href="http://cooltext.com" target="_top"><img src="https://cooltext.com/images/ct_button.gif" width="88" height="31" alt="Cool Text: Logo and Graphics Generator" /></a>