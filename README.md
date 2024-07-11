# CPU Profile Summarizer

This tool is designed to summarize CPU profiling data for use in generating dataset prompts, providing insights into function execution times and their impact on CPU usage.

## Prerequisites

Before you can use the CPU Profile Summarizer, ensure you have Node.js installed on your system. You can download and install Node.js from [https://nodejs.org/](https://nodejs.org/).

## Installation

No installation is required. Simply clone or download the repository containing the tool to your local machine.

## Usage

To use the CPU Profile Summarizer, follow these steps:

1. Open a terminal or command prompt.
2. Navigate to the directory containing the `index.js` file of the CPU Profile Summarizer.
3. Run the tool using Node.js, passing the path to the CPU profile JSON file as an argument:

```bash
node index.js <path-to-cpu-profile.cpuprofile>
```

Replace <path-to-cpu-profile.cpuprofile> with the actual path to your CPU profile JSON file.

For example:

```bash
node index.js profiles/myAppProfile.cpuprofile
```

The tool will process the CPU profile and generate a summary file in the summaries directory, located in the same directory as index.js. The summary file will be named after the original profile file, with a .summary.json extension.

## Output

The summary file contains the following information:

topSelfTimeFunctions: Functions with the highest self execution times.
topTotalTimeFunctions: Functions with the highest total execution times.
startTime: The start time of the profiling session, in seconds.
endTime: The end time of the profiling session, in seconds.

Each function in the topSelfTimeFunctions and topTotalTimeFunctions lists includes:

functionName: The name of the function.
totalTime: The total execution time of the function, in seconds.
hitCount: The number of times the function was executed.
selfTime: The self execution time of the function, in seconds.
url: The URL of the script containing the function.
selfTimePercentage: The percentage of the highest self time relative to the total profile duration.
totalTimePercentage: The percentage of the highest total time relative to the total profile duration.