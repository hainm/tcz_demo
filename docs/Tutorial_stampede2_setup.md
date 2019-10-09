Configure your Stampede2 account to use TCZ module 
=============================================

## Edit .bashrc

Add three module commands (see below) in the `$HOME/.bashrc` file

```
############
# SECTION 1
#
# There are three independent and safe ways to modify the standard
# module setup. Below are three ways from the simplest to hardest.
#   a) Use "module save"  (see "module help" for details).
#   b) Place module commands in ~/.modules
#   c) Place module commands in this file inside the if block below.
#
# Note that you should only do one of the above.  You do not want
# to override the inherited module environment by having module
# commands outside of the if block[3].

if [ -z "$__BASHRC_SOURCED__" -a "$ENVIRONMENT" != BATCH ]; then
  export __BASHRC_SOURCED__=1

  ##################################################################
  # **** PLACE MODULE COMMANDS HERE and ONLY HERE.              ****
  ##################################################################

  module use /scratch/05392/cylu/tcz_demo/packages/modulefiles
  module use /scratch/05392/cylu/tcz_demo/modulefiles
  module load tcz
fi

```

---

Go to: [Home](../README.md), [Software](./Software.md), [Tutorials](./Tutorials.md), [Examples](./Examples.md), [FAQ](./Faq.md)