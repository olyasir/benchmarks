---
layout: home
title: Welcome to Benchmark Results
---

# Model Benchmark Results

This site contains benchmark results for various models. Below you'll find the latest results:

## Latest Results

Debug info:
- Number of results: {{ site.results | size }}
- Results files: {% for result in site.results %}{{ result.path }}, {% endfor %}
- Collection dir: {{ site.collections.results.directory }}
- Collection files: {% for file in site.collections.results.files %}{{ file.path }}, {% endfor %}

{% assign sorted_results = site.results | sort: 'date' | reverse %}
{% for result in sorted_results %}
### [{{ result.title }}]({{ site.baseurl }}{{ result.url }})
- **Date:** {{ result.date | date: "%B %d, %Y" }}
- **Model Version:** {{ result.version | default: "1.0" }}
- **Key Metrics:**
  - Accuracy: {{ result.accuracy | default: "N/A" }}
  - Latency: {{ result.latency | default: "N/A" }}
  - Throughput: {{ result.throughput | default: "N/A" }}

{% endfor %}

## How to Read Results

Each benchmark result includes:
- Detailed performance metrics
- Test conditions and environment
- Comparative analysis
- Recommendations

Click on any result above to view the full details. 