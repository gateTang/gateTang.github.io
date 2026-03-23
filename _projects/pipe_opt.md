---
title: 'PipeOpt - Automated Pipeline Register Insertion via ILP-Based Static Timing Analysis Optimization'
date: 2026-01-01
permalink: /projects/pipe_opt/
---
<!-- [Link to GitHub](https://github.com/gateTang/) -->

Background
======
In the digital IC tapeout process, setup timing violations that are identified in the static timing analysis (STA) report can be fixed by <b>pipelining</b>, a process of splitting the long combinational logic into smaller submodules of combinational logic to shorten the combinational delay. Through reducing the combinational delay, setup time violations can be avoided.

<div style="text-align: center;"> <img src="/images/setup_time_violation_img.png"></div>

Pipelining is achieved through inserting more registers between combinational logic which inherently sacrifices latency for reduced combinational delay and avoidance of setup violations. 

The process of inserting more registers involves a lengthy collaboration between digital designers and physical designers to identify the setup violations and manually mapping it to ideal register insertion points. This is further exacerbated when designing at a larger scale.

PipeOpt is designed to automate the manual process between physical design timing violation analysis and RTL modification during tapeout process.

About PipeOpt
======
PipeOpt is a Python CLI tool that analyzes Cadence Innovus static timing analysis (STA) reports, netlists, and floorplan reports to identify the optimal register insertion points for a chosen RTL module. 

Specifically PipeOpt applies a binary integer linear program (ILP) to recommend optimal register insertion points which resolve timing violations while minimizing for registers inserted. PipeOpt then maps the insertion points to its corresponding RTL signals through anlayzing the netlist.

<div style="text-align: center;"> <img src="/images/pipe_opt_diagram.png"></div>


PipeOpt is a sub-project of SiliconJackets and is aimed to be applied to SiliconJacket's Tapeouts 1, 2, and 3.