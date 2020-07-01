---
layout: post
title:  "How to install Flutter"
date:   2020-07-01 19:41:03 +0530
categories: jekyll update
comments: true
permalink: "/flutterinstall"
---
Select the operating system on which you are installing Flutter:<br>
[windows] <i class="fab fa-windows"></i>    [MacOS] <i class="fab fa-apple"></i>    [Linux] <i class="fab fa-linux"></i>

## For Windows
### System requirements
To install and run Flutter, your development environment must meet these minimum requirements:
* **Operating Systems:** Windows 7 SP1 or later (64-bit)
* **Disk Space:** 400 MB (does not include disk space for IDE/tools).
* **Tools:** Flutter depends on these tools being available in your environment.
  * [Windows PowerShell 5.0] or newer (this is pre-installed with Windows 10)
  * [Git for Windows] 2.x, with the **Use Git from the Windows Command Prompt** option.
  
    If Git for Windows is already installed, make sure you can run `git` commands from the command prompt or PowerShell.

### Get the Flutter SDK
- Download the following installation bundle to get the latest stable release of the Flutter SDK:
   For `other release channels`, and `older builds`, see the [SDK archive] page.
- Extract the zip file and place the contained flutter in the desired installation location for the Flutter SDK (for example, `C:\src\flutter;` do not install Flutter in a directory like `C:\Program Files\` that requires elevated privileges).
- If you don’t want to install a fixed version of the installation bundle, you can `skip` steps 1 and 2. Instead, get the source code from the [Flutter repo] on GitHub, and change branches or tags as needed. For example:
{% highlight ruby %}
git clone https://github.com/flutter/flutter.git -b stable
{% endhighlight %}
You are now ready to run Flutter commands in the Flutter Console.
### Update your path
If you wish to run Flutter commands in the regular Windows console, take these steps to add Flutter to the `PATH` environment variable:
* From the Start search bar, enter ‘env’ and select **Edit environment variables for your account**.
* Under **User variables** check if there is an entry called **Path**:
    * If the entry exists, append the full path to `flutter\bin` using ; as a separator from existing values.
    * If the entry doesn’t exist, create a new user variable named `Path` with the full path to `flutter\bin` as its value.
<br>

You have to close and reopen any existing console windows for these changes to take effect.

### Run flutter doctor
From a console window that has the Flutter directory in the path (see above), run the following command to see if there are any platform dependencies you need to complete the setup:
{% highlight ruby %}
C:\src\flutter>flutter doctor
{% endhighlight %}
This command checks your environment and displays a report of the status of your Flutter installation. Check the output carefully for other software you might need to install or further tasks to perform (shown in X mark).

For example:

{% highlight ruby %}
[-] Android toolchain - develop for Android devices
    • Android SDK at D:\Android\sdk
    ✗ Android SDK is missing command line tools; download from https://goo.gl/XxQghQ
    • Try re-installing or updating your Android SDK,
      visit https://flutter.dev/setup/#android-setup for detailed instructions.
{% endhighlight %}

## For MacOS
To install and run Flutter, your development environment must meet these minimum requirements:

* **Operating Systems:** macOS (64-bit)
* **Disk Space:** 2.8 GB (does not include disk space for IDE/tools).
* **Tools:** Flutter depends on these command-line tools being available in your environment.
    * `bash`
    * `curl`
    * `git` 2.x
    * `mkdir`
    *  `rm`
    * `unzip`
    * `which`
    * `zip`

### Get the Flutter SDK
* Download the following installation bundle to get the latest stable release of the Flutter SDK:
  For other release channels, and older builds, see the [SDK archive] page.
* Extract the file in the desired location, for example:
{% highlight ruby %}
 $ cd ~/development
 $ unzip ~/Downloads/flutter_macos_1.17.4-stable.zip
{% endhighlight %}
* If you don’t want to install a fixed version of the installation bundle, you can skip steps 1 and 2. Instead, get the source code from the [Flutter repo] on GitHub with the following command:
{% highlight ruby %}
$ git clone https://github.com/flutter/flutter.git
{% endhighlight %}
You can also change branches or tags as needed. For example, to get just the stable version:
{% highlight ruby %}
$  git clone https://github.com/flutter/flutter.git -b stable --depth 1
{% endhighlight %}
Add the `flutter tool` to your path:
{% highlight ruby %}
$  export PATH="$PATH:`pwd`/flutter/bin"
{% endhighlight %}
This command sets your `PATH` variable for the current terminal window only. To permanently add Flutter to your path, see [Update your path].
* Optionally, pre-download development binaries:

The flutter tool downloads platform-specific development binaries as needed. For scenarios where pre-downloading these artifacts is preferable (for example, in hermetic build environments, or with intermittent network availability), iOS and Android binaries can be downloaded ahead of time by running:
{% highlight ruby %}
$  flutter precache
{% endhighlight %}
For additional download options, see `flutter help precache`.

You are now ready to run Flutter commands!

### Run flutter doctor

Run the following command to see if there are any dependencies you need to install to complete the setup (for verbose output, add the `-v` flag):
{% highlight ruby %}
$  flutter doctor
{% endhighlight %}

This command checks your environment and displays a report to the terminal window. The Dart SDK is bundled with Flutter; it is not necessary to install Dart separately. Check the output carefully for other software you might need to install or further tasks to perform (shown in X mark).

For example:

{% highlight ruby %}
[-] Android toolchain - develop for Android devices
    • Android SDK at /Users/obiwan/Library/Android/sdk
    ✗ Android SDK is missing command line tools; download from https://goo.gl/XxQghQ
    • Try re-installing or updating your Android SDK,
      visit https://flutter.dev/setup/#android-setup for detailed instructions.
{% endhighlight %}
The following sections describe how to perform these tasks and finish the setup process.

Once you have installed any missing dependencies, run the flutter doctor command again to verify that you’ve set everything up correctly.

### Update your path
You can update your PATH variable for the current session at the command line, as shown in [Get the Flutter SDK]. You’ll probably want to update this variable permanently, so you can run `flutter` commands in any terminal session.

The steps for modifying this variable permanently for all terminal sessions are machine-specific. Typically you add a line to a file that is executed whenever you open a new window. For example:
* Determine the directory where you placed the Flutter SDK. You need this in Step 3.
* Open (or create) the rc file for your shell. Typing `echo $SHELL` in your Terminal tells you which shell you’re using. If you’re using  Bash, edit `$HOME/.bash_profile` or `$HOME/.bashrc.` If you’re using Z shell, edit `$HOME/.zshrc`. If you’re using a different shell, the    file path and filename will be different on your machine.
* Add the following line and change `PATH_TO_FLUTTER_GIT_DIRECTORY` to be the path where you cloned Flutter’s git repo:
{% highlight ruby %}
$ export PATH="$PATH:[PATH_TO_FLUTTER_GIT_DIRECTORY]/flutter/bin"
{% endhighlight %}
* Run source $HOME/.<rc file> to refresh the current window, or open a new terminal window to automatically source the file.
* Verify that the flutter/bin directory is now in your PATH by running:
{% highlight ruby %}
$ echo $PATH
{% endhighlight %}
Verify that the flutter command is available by running:
{% highlight ruby %}
$ which flutter
{% endhighlight %}

# For LINUX
###System requirements
To install and run Flutter, your development environment must meet these minimum requirements:

* **Operating Systems:** Linux (64-bit)
* **Disk Space:** 600 MB (does not include disk space for IDE/tools).
* **Tools:** Flutter depends on these command-line tools being available in your environment.
    * `bash`
    * `curl`
    * `file`
    * `git` 2.x
    * `mkdir`
    * `rm`
    * `unzip`
    * `which`
    * `xz-utils`
    * `zip`
* **Shared libraries:** Flutter `test` command depends on this library being available in your environment.
    * `libGLU.so.1` - provided by mesa packages such as `libglu1-mesa` on Ubuntu/Debian
### Get the Flutter SDK
* Download the following installation bundle to get the latest stable release of the Flutter SDK:
For other release channels, and older builds, see the [SDK archive] page.
* Extract the file in the desired location, for example:
{% highlight ruby %}
$  cd ~/development
$  tar xf ~/Downloads/flutter_linux_1.17.4-stable.tar.xz
{% endhighlight %}
If you don’t want to install a fixed version of the installation bundle, you can skip steps 1 and 2. Instead, get the source code from the [Flutter repo] on GitHub with the following command:
{% highlight ruby %}
$  git clone https://github.com/flutter/flutter.git
{% endhighlight %}
You can also change branches or tags as needed. For example, to get just the stable version:
{% highlight ruby %}
$  git clone https://github.com/flutter/flutter.git -b stable --depth 1
{% endhighlight %}
* Add the flutter tool to your path:
{% highlight ruby %}
$  export PATH="$PATH:`pwd`/flutter/bin"
{% endhighlight %}
This command sets your PATH variable for the current terminal window only. To permanently add Flutter to your path, see [Update your path].
* Optionally, pre-download development binaries:

The `flutter` tool downloads platform-specific development binaries as needed. For scenarios where pre-downloading these artifacts is preferable (for example, in hermetic build environments, or with intermittent network availability), iOS and Android binaries can be downloaded ahead of time by running:
{% highlight ruby %}
$ flutter precache
{% endhighlight %}
For additional download options, see `flutter help precache.`

You are now ready to run Flutter commands!
### Run flutter doctor

Run the following command to see if there are any dependencies you need to install to complete the setup (for verbose output, add the `-v` flag):
{% highlight ruby %}
$  flutter doctor
{% endhighlight %}

This command checks your environment and displays a report to the terminal window. The Dart SDK is bundled with Flutter; it is not necessary to install Dart separately. Check the output carefully for other software you might need to install or further tasks to perform (shown in X mark).

For example:

{% highlight ruby %}
[-] Android toolchain - develop for Android devices
    • Android SDK at /Users/obiwan/Library/Android/sdk
    ✗ Android SDK is missing command line tools; download from https://goo.gl/XxQghQ
    • Try re-installing or updating your Android SDK,
      visit https://flutter.dev/setup/#android-setup for detailed instructions.
{% endhighlight %}
The following sections describe how to perform these tasks and finish the setup process.

Once you have installed any missing dependencies, run the flutter doctor command again to verify that you’ve set everything up correctly.
### Update your path
You can update your PATH variable for the current session at the command line, as shown in [Get the Flutter SDK]. You’ll probably want to update this variable permanently, so you can run `flutter` commands in any terminal session.

The steps for modifying this variable permanently for all terminal sessions are machine-specific. Typically you add a line to a file that is executed whenever you open a new window. For example:

* Determine the directory where you placed the Flutter SDK. You need this in Step 3.
* Open (or create) the rc file for your shell. For example, Linux uses the Bash shell by default, so edit `$HOME/.bashrc`. If you are using a different shell, the file path and filename will be different on your machine.
* Add the following line and change `PATH_TO_FLUTTER_GIT_DIRECTORY` to be the path where you cloned Flutter’s git repo:
{% highlight ruby %}
$ export PATH="$PATH:[PATH_TO_FLUTTER_GIT_DIRECTORY]/flutter/bin"
{% endhighlight %}
* Run source `$HOME/.<rc file>` to refresh the current window, or open a new terminal window to automatically source the file.
* Verify that the `flutter/bin` directory is now in your PATH by running:
{% highlight ruby %}
$  echo $PATH
{% endhighlight %}
Verify that the `flutter` command is available by running:
{% highlight ruby %}
$  which flutter
{% endhighlight %}

[windows]: https://flutter.dev/docs/get-started/install/windows
[MacOS]: https://flutter.dev/docs/get-started/install/macos
[Linux]: https://flutter.dev/docs/get-started/install/linux
[Windows PowerShell 5.0]: https://docs.microsoft.com/en-us/powershell/scripting/install/installing-windows-powershell
[Git for Windows]: https://git-scm.com/download/win
[SDK archive]: https://flutter.dev/docs/development/tools/sdk/archive
[Flutter repo]: https://github.com/flutter/flutter
[Update your path]: https://flutter.dev/docs/get-started/install/macos#update-your-path
[Get the Flutter SDK]: https://flutter.dev/docs/get-started/install/macos#get-sdk