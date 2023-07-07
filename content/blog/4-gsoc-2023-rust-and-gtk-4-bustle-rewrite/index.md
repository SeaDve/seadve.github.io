+++
title = "GSoC 2023: Rust and GTK 4 Bustle Rewrite (Week 3 & 4)"
date = 2023-07-05
updated = 2023-07-07

[taxonomies]
tags = ["GSoC"]
+++

![Thumbnail](thumbnail.png)

## Progress Made

There's unfortunately not a lot to talk about for the past two weeks as I have been really absorbed with finals at my university. However, while preparing for the finals, we got the [PR to add `from_bytes` constructor for `zbus::Message`](https://github.com/dbus2/zbus/pull/370) merged. This means that we can now construct `zbus::Message` from raw `GDBusMessage` bytes and vice versa, which is critical for porting Bustle from GDBus to zbus. On the other hand, the [PR to implement Display for Value, Array, Structure, Dict & Maybe](https://github.com/dbus2/zbus/pull/379) is, while the implementation for `zbus::Value::Str` and `zbus::Value::Array` is already fixed, still on the review stage as there are still things to polish, such as figuring out a way to simplify the implementation.

Meanwhile, I have also been experimenting with drawing on the diagram using GTK transform functions such as `translate_coordinates` and `compute_point`, but nothing is ready enough yet for a screenshot.

## Plans for the Following Weeks

With my finals out of the equation, I could focus more on finishing up drawing the signals and methods arrow on the diagram during the last days on GSoC midterm period.

I will also push [PR to implement Display for Value, Array, Structure, Dict & Maybe](https://github.com/dbus2/zbus/pull/379) to be merged so that the [zbus port MR](https://gitlab.gnome.org/msandova/bustle/-/merge_requests/2) can also be merged.

<br>

That's all for this week. I'm looking forward to writing more in the next weeks. Thanks for reading!
