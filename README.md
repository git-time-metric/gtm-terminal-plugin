![GTM Logo](https://raw.githubusercontent.com/git-time-metric/gtm-atom-plugin/master/lib/GTMLogo-128.png)
# Terminal Git Time Metrics (GTM) plug-in
### Simple, seamless, lightweight time tracking for all your git projects

Git Time Metrics (GTM) is a tool to automatically track time spent reading and working on code that you store in a Git repository. By installing GTM and using supported plug-ins for your favorite editors, you can immediately realize better insight into how you are spending your time and on what files.

### Installation

Installing GTM is a two step process.  First, it's recommended you install the GTM executable that the plug-in integrates with and then install the Terminal GTM plug-in.  Please submit an issue if you have any problems and/or questions.

1. Follow the [Getting Started](https://github.com/git-time-metric/gtm/blob/master/README.md) section to install the GTM executable for your operating system.
2. To install the plugin download the shell script and `source gtm-plugin.sh` from either your .bashrc or .zshrc file. Also make sure the shell script is executable `chmod +x gtm-plugin.sh`.

**Note** - to enable time tracking for a Git repository, you need to initialize it with `gtm init` otherwise it will be ignored by GTM. This is done via the command line.
```
> cd /path/to/your/project
> gtm init
```

Consult the [README](https://github.com/git-time-metric/gtm/blob/master/README.md) and [Wiki](https://github.com/git-time-metric/gtm/wiki) for more information.

**Note** - to use this plugin you must be on GTM version 1.1-beta.1 or higher.  To enable terminal tracking on an existing GTM initialized Git repository reinitialize with `gtm init`. To disable terminal tracking for a git repostiory use `gtm init --terminal=false`. 

# Features

### Reporting

The time spent in the terminal is included when using the `gtm report` command.
```
> gtm report

72b7917 Output golang info for appveyor build
Sat Sep 10 21:30:27 2016 -0500 Michael Schenk

       12m 50s  [r] Terminal
        6m  0s  [r] script/appveyor-build.sh
        2m 10s  [m] appveyor.yml
       21m  0s
```

### Terminal Prompt

The total time spent for in-process work (uncommitted) is exported to `GTM_STATUS` environment variable. Your terminal prompt can be configured to display the current status.

![](https://cloud.githubusercontent.com/assets/630550/18611230/afa8a248-7cf8-11e6-9436-ad5eccbfa500.png)

### Command Line Interface

Use the command line to report on time logged for your commits.

Here are some examples of insights GTM can provide you.

**Git commits with time spent**
```
> gtm report -total-only -n 3

9361c18 Rename packages
Sun Jun 19 09:56:40 2016 -0500 Michael Schenk  34m 30s

341bd77 Vagrant file for testing on Linux
Sun Jun 19 09:43:47 2016 -0500 Michael Schenk  1h 16m  0s

792ba19 Require a 40 char SHA commit hash
Thu Jun 16 22:28:45 2016 -0500 Michael Schenk  1h  1m  0s
```

**Git commits with detailed time spent by file**
```
> gtm report

b2d16c8 Refactor discovering of paths when recording events
Thu Jun 16 11:08:47 2016 -0500 Michael Schenk

       30m 18s  [m] event/event.go
       12m 31s  [m] event/manager.go
        3m 14s  [m] project/project.go
        1m 12s  [r] .git/COMMIT_EDITMSG
        1m  0s  [r] .git/index
           25s  [r] event/manager_test.go
           20s  [r] metric/manager.go
       49m  0s
```

**Timeline of time spent by day**
```
> gtm report --format timeline -n 3

           0123456789012345678901234
Fri Jun 24 *                              22m  0s
Sat Jun 25 **                          1h 28m  0s
Sun Jun 26 ****                        3h 28m  0s
Mon Jun 27 *                               4m  0s
Tue Jun 28 **                          1h 36m  0s
                                       6h 58m  0s
```

# Support

To report a bug, please submit an issue on the [GitHub Page](https://github.com/git-time-metric/gtm-vim-plugin/issues)

Consult the [README](https://github.com/git-time-metric/gtm/blob/master/README.md) and [Wiki](https://github.com/git-time-metric/gtm/wiki) for more information.
