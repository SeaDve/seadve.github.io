+++
title = "GSoC 2023: Rust and GTK 4 Bustle Rewrite (Final Overview)"
date = 2023-08-28T12:29:00.001+08:00
updated = 2023-08-28T12:29:00.002+08:00

[taxonomies]
tags = ["GSoC 2023"]
+++

![Thumbnail](thumbnail.png)

Over the summer, I worked on rewriting Bustle in Rust and GTK 4 as part of the Google Summer of Code (GSoC) 2023 program. This post is an overview of the work done and the future plans for the project.

## The Project

The ultimate goal of this project is to port [Bustle](https://gitlab.freedesktop.org/bustle/bustle), a graphical application used to analyze [D-Bus](https://www.freedesktop.org/wiki/Software/dbus/) activities, to GTK 4 and rewrite it in Rust.

![Old Bustle](old-bustle.png)

Although the current implementation of Bustle in Haskell and GTK 3 is functional, there are compelling reasons to consider a rewrite in Rust. This includes enabling the tool to take advantage of a range of ergonomic libraries, including [zbus](https://github.com/dbus2/zbus), [gtk4-rs](https://github.com/gtk-rs/gtk4-rs), and [pcap-file](https://github.com/courvoif/pcap-file), that would ease the burden in maintenance. Furthermore, the growing Rust community and the availability of the Rust SDK in [Flathub](https://flathub.org/) would make the tool more accessible to potential contributors and simpler to distribute to users.

Porting the tool to [GTK 4](https://www.gtk.org/), on the other hand, would offer several benefits, such as access to newer and more performant widgets like `ListView`. This would allow Bustle to benefit from the latest developments in the platform and remain current with evolving standards.

Altogether, a rewrite of Bustle in Rust and GTK 4 would provide advantages that could enhance the tool's functionality, maintainability, longevity, accessibility, and possibly efficiency.

## Work Done

Most of the tasks in the original proposal have been completed. This includes having an initial MVP, porting GDBus usage to zbus, implementing file loading and saving, completing the recording functionality, and porting the UI, which comprises the diagram, details view, and services filter, to GTK 4.

For more details on the work done, I posted [bi-weekly updates](https://seadve.github.io/tags/gsoc-2023/) on my blog.

### Snapshots

#### Diagram and Details View

![Diagram and Details View](diagram-and-details-view.gif)

#### Recording and Services Filter

![Recording and Services Filter](recording-and-services-filter.gif)

## Code Merged

These are the summary of code that has been merged during the GSoC period.

### Bustle

Most of the work done is in the [Bustle GNOME GitLab repository](https://gitlab.gnome.org/msandova/bustle), where the following pull requests have been merged:

* [Basic parsing and diagram implementation](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/1)
* [Port to zbus](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/2)
* [Drop explicit cargo protocol setting](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/3)
* [Decouple recording monitor from DiagramModel](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/10)
* [Implement system and address monitoring and recording](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/12)
* [Load DiagramModel from file asynchronously](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/13)
* [Stick at the bottom when an item is added to the diagram](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/14)
* [Bump gtk4-rs version](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/15)
* [Improve timestamp accuracy](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/18)
* [Focus on the entry row when dialog presents](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/19)
* [Save DiagramModel to file asynchronously](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/21)
* [Further improve timestamp accuracy](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/22)
* [Handle undefined behavior](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/23)
* [Enable link-time optimization and various cleanups](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/26)
* [Add loading and waiting pages on the window](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/30)
* [Show a toast when clicking copy and other fixes](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/33)
* [Implement diagram columns, arrows, and arcs](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/34)
* [Improve loading performance and code organization](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/35)
* [Implement API to get well-known names from bus names](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/36)
* [Refactor name owner changed signal handling](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/37)
* [Organize diagram files](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/39)
* [Improve file naming](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/40)
* [Monitor code cleanups](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/41)
* [Add support for targeted signals](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/42)
* [Port from libpcap to pcap-file](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/43)
* [Use a more proper column width](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/44)
* [Improving diagram tag styling](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/46)
* [Properly update the color and label of RowTag](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/47)
* [Improving diagram styling](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/48)
* [Propagate errors to the user](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/50)
* [Only show errors when necessary](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/51)
* [Prevent copy when packet data is owned](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/52)
* [Fix DiagramHeader labels UI glitch](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/54)
* [ColorWidget and DiagramView cleanups](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/55)

### Zbus and Gtk4-rs

While the project is focused on Bustle, some changes are necessary to be upstreamed to other projects. This includes changes to zbus and gtk4-rs, where the following pull requests have been merged:

#### Zbus

* [zb: Add a from_bytes constructor for Message](https://github.com/dbus2/zbus/pull/370)
* [zv: impl Display implementation for Value, Array, Structure, Dict & Maybe](https://github.com/dbus2/zbus/pull/379)
* [zv, zn: Improve Str, Owned*Name, BusName Debug implementations](https://github.com/dbus2/zbus/pull/450)

#### Gtk4-rs

* [gdk: Make RGBA::new const and add with_* constructors](https://github.com/gtk-rs/gtk4-rs/pull/1468)

## Code to be Merged

Due to time constraints and unexpected issues, some of the pull requests are still pending review. The following pull requests are still open:

### Bustle

* [Implement services filter](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/49)
* [Port to GskPath APIs](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/53)
* [Make use of GtkMapListModel for layouts](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/56)
* [Implement BusNameList and FilteredBusNameModel](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/57)
* [Fix header expanded height computation](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/58)

## Future Plans

While most of the tasks in the proposal have been completed, there are still a few things that need to be done. This includes the following:

1. Optimizing performance
2. Hunting and squashing bugs
   1. Improving name owner changed signal handling
   2. Drawing method call arc regardless if the row is not drawable
   3. Properly killing the `dbus-monitor` process
3. Adding more features:
   1. Adding a button that scrolls to the method call message of a method return message or vice-versa
   2. Adding a way to open multiple diagrams at once via tabs and multiple windows
4. Continuous involvement and contribution to the open-source community

## Acknowledgments

I would like to express my gratitude to my mentors Bilal Elmoussaoui and Maximiliano Sandoval, for tirelessly reviewing my pull requests and guiding me. I would also like to thank the GNOME Foundation and the community, especially the GNOME GSoC Admin, Felipe Borges, for giving me the opportunity to work on this project. I would also like to extend my appreciation to zbus maintainer, Zeeshan Ali, for their help in getting my pull requests merged against zbus. Finally, I would like to thank my family and friends for their support and encouragement.


