---
description: Select the AI model in a profile to include in benchmark testing.
---

# Select the AI Model in a Profile

## Overview

When [adding a profile](add-a-profile-to-the-profiler.md) to the [Profiler](what-is-the-profiler.md), by default that profile uses the [underlying AI model](../model-settings/view-underlying-ai-model-settings.md) for that AI. Select another AI model to that profile. Select another AI model in any displayed profile anytime an active benchmarking test is not running.

## Select the AI Model in a Profile

1. [View the Profiler](view-the-profiler.md).
2. [Add a profile](add-a-profile-to-the-profiler.md) or select the currently profiled AI model in a pane.
3. Change any of these settings:
   * From the **Model** drop-down menu, select which AI model to profile. See the [types of AI models](../model-settings/types-of-ai-models.md).
   * From the **Temperature** drop-down menu, enter the temperature in which to set the AI model. See the [Temperature overview](../model-settings/adjust-ai-model-temperature-settings.md#overview) for more information.
   * From the **Max Response Tokens** drop-down menu, enter the max number of tokens. See the [Max Response Tokens overview](../model-settings/adjust-ai-model-max-response-size.md#overview) for more information.
4. Select the **Done** button.
5. [Benchmark the profiles](benchmark-the-profiles-in-the-profiler.md).

## Best Practice

Use the same temperature and max response tokens for each AI model in the benchmark test. Using different settings does not benchmarking using the same metrics and affects the test results.
