# Redkite

#### Description

Redkite is a small free software and cross-platform GUI toolkit.
It is developed in C++11&14 and inspired from other
well known GUI toolkits.

Version: 0.9
License: GPLv3
Author: Iurie Nistor
Status: active development, no release yet

#### The problem

An application that is developed in a particular GUI toolkit
is loading in its address space GUI plugins that are developed
in a different GUI toolkit, or different versions of a particular
toolkit. The well known GUI toolkits were not designed with
this scenario in mind, and this will cause difficulties, problems,
even crashes. Redkite GUI toolkit is developed to address this problem,
and provide a way to develop easily self-sufficient GUI plugins apart
from developing of standalone applications. Most often these kinds
of problems arise in music software, for example, when a Digital
Audio Workstation as a host is loading audio GUI plugins.

### Goals

 * Generally to have the same basic properties as common GUI toolkits.

 * Many instances of the same toolkit version or different must be able
  to run without problems in the same process address space.

 * Can be linked statically into a shared library that uses the toolkit
  and that shared library to be loaded dynamically by the host.
  Loading these kinds of shared libraries (linked against the same
  toolkit version or not) in the same address process space must run
  without problems, there must be no interference between
  toolkit instances and versions.

 * Not to add dependences that breaks the above two points.

 * Can be easily linked statically.

 * Be cross-platform

 * User interface API to be simple

### What was implemented

* Widgets: RkWidget, RkLabel
* Graphics: RkPainter, RkImage. RkPainter paints on RkWidget and RkImage.
  RkPainter uses Cairo backend.
* Actions: a binding mechanism between objects. An action can be posted in thread-safe manner.
* Cross-platform: GNU/Linux (X11), Windows (Win API). No plans for Mac now.
* CMake system, build/install
* rkpng2c - a tool that converts PNG images to C array encoded in ARGB32

Interface classes that now are implemented with the purpose of extending their functionality:

* RkCanvas
* RkColor
* RkEvent
* RkEventQueue
* RkImage
* RkLabel
* RkLog
* RkMain
* RkPainter
* RkPen
* RkFont
* RkPlatform
* RkPoint
* RkRealPoint
* RkRect
* RkSize
* RkWidget

### What applications were developed with Redkite?

* [Geonkick](https://gitlab.com/quamplex/geonkick) - a percussion synthesizer is
in the process of migrating from Qt to Redkite. See "devel" branch.

