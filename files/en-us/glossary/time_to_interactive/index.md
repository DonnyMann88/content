---
title: Time to Interactive (TTI)
slug: Glossary/Time_to_interactive
page-type: glossary-definition
sidebar: glossarysidebar
---

**Time to Interactive** (**TTI**) is a non-standardized web performance 'progress' metric defined as the point in time when the last [Long Task](/en-US/docs/Web/API/PerformanceLongTaskTiming) finished and was followed by 5 seconds of network and main thread inactivity.

TTI, proposed by the Web Incubator Community Group in 2018, was intended to provide a metric that describes when a page or application contains useful content and the main thread is idle and free to respond to user interactions, including having event handlers registered.

#### Caveat

TTI is derived by leveraging information from the [Long Task API](/en-US/docs/Web/API/PerformanceLongTaskTiming). Although available in some performance monitoring tools, TTI is not a part of any official web specification.

## See also

- [Definition of TTI](https://github.com/WICG/time-to-interactive) from Web Incubator Community Group
- [Time to Interactive — focusing on human-centric metrics](https://calibreapp.com/blog/time-to-interactive) by Radimir Bitsov
- {{glossary("Time_to_first_byte", "Time to first byte (TTFB)")}}
