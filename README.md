﻿# SpecFlow.SimpleInjector
SpecFlow plugin for using SimpleInjector as a dependency injection framework for step definitions.

Currently supports
* SpecFlow v2.1
* SimpleInjector v3.0 or above

License: Apache (https://github.com/jguc/SpecFlow.SimpleInjector/blob/master/LICENSE)

NuGet: https://www.nuget.org/packages/SpecFlow.SimpleInjector

## Usage

Install plugin from NuGet into your SpecFlow project.

    PM> Install-Package SpecFlow.SimpleInjector
  
Create a static method somewhere in the SpecFlow project (recommended to put it into the `Support` folder) that returns an SimpleInjector `Container` and tag it with the `[ScenarioDependencies]` attribute. Configure your dependencies for the scenario execution within the method.

A typical dependency builder method probably looks like this:

    [ScenarioDependencies]
    public static ContainerBuilder CreateContainerBuilder()
    {
      // create container with the runtime dependencies
      var builder = Dependencies.CreateContainerBuilder();

      //TODO: add customizations, stubs required for testing
	  builder.Verify();
      
      return builder;
    }

## Plugin based on 

http://gasparnagy.com/2016/08/specflow-tips-customizing-dependency-injection-with-autofac/
