# Hangfire.Console.Extensions
[![NuGet version](https://badge.fury.io/nu/Hangfire.Console.Extensions.svg)](https://badge.fury.io/nu/Hangfire.Console.Extensions)

## Features

 - Makes it easier to use `Hangfire.Console` with .net core dependency injection

## Setup

In .NET Core's Startup.cs:
```c#
public void ConfigureServices(IServiceCollection services)
{
    services.AddHangfireConsoleExtensions();
}
```

## Starting a job
To start a job you can use the `IJobManager`, it will automatically check if you are currently inside a job, if that is the case it will mark the started job as a Continuation.

## Log
Instead of logging using the extension method on `PerformContext` you can now just use the `ILogging` and it will get logged to both normal logging facilities and Hangfire.Console.

## Progressbar
To create a progress bar you can use `IProgressBarFactory`.

## IJobCancellationToken
Just take the `IJobCancellationToken` as a constructor parameter to get a hold of the cancellation token.

## Schedule jobs
Contains a extension method for `AddOrUpdateManuallyTriggered` if you have a job that should only be run manually.