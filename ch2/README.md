# Chapter 2: The Lay of The Land

## KEYWORDS


## SUMMARY

### Introduction

* Think of a web server as a function;
  * A URL typed in a browser -> think as a call to a function in a remote server;
  * This function handles the request and returns a response.

### Simple Functions

* Phoenix is built with Elixir, e.g., a couple of functions:
```elixir
  def inc(x), do: x + 1
  def dec(x), do: x - 1
```
* In Elixir, it's possible to chain functions. e.g. :
```elixir
  2 |> inc |> inc |> dec
```
  * |>, or _pipe operator_, pass the value of left as the first argument to the function on the right;
  * These compositions are called **_pipes_** or **_pipelines_**;
  * Each individual part is called **_segment_** or **_pipe segment_**;
  * **_Pipelines_ and each _segment_ are functions**;
    * This means that we can build **_pipelines_** of **_pipelines_**.
* In Phoenix, everything starts with a **_connection_**;
```elixir
  connection |> phoenix
```
  * This **_connection_** comes with information about the request;
  * Phoenix handles the **_connection_** with a series of **_pipelines_** and returns with a response.
    * That's **how every layer of Phoenix works**: functions call other functions and the first argument of every function is the **_connection_**.

#### Inside controllers

* A _controller_ is where an _action_ is placed;
* An _action_ is a function that handles requests.

---

### Building a Feature

* Routes in Phoenix go in **web/router.ex** by default, i.e. [./hello/web/router.ex](./hello/web/router.ex);
* All controllers are in **web/controllers**;
* A template has the extension **_eex_**;
  * Phoenix compiles it into a function.
