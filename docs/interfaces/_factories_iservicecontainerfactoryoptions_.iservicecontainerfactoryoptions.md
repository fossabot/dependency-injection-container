[dependency-injection-container - v0.0.1](../README.md) › [Globals](../globals.md) › ["factories/IServiceContainerFactoryOptions"](../modules/_factories_iservicecontainerfactoryoptions_.md) › [IServiceContainerFactoryOptions](_factories_iservicecontainerfactoryoptions_.iservicecontainerfactoryoptions.md)

# Interface: IServiceContainerFactoryOptions

Represents options of IServiceContainerFactory.

## Hierarchy

* **IServiceContainerFactoryOptions**

## Index

### Properties

* [useReflection](_factories_iservicecontainerfactoryoptions_.iservicecontainerfactoryoptions.md#usereflection)

## Properties

###  useReflection

• **useReflection**: *boolean*

*Defined in [src/factories/IServiceContainerFactoryOptions.ts:10](https://github.com/botflux/dependency-injection-container/blob/8392867/src/factories/IServiceContainerFactoryOptions.ts#L10)*

If true the ServiceContainerFactory will returns a service container
handling metadata and decorators; otherwise it will returns a plain
service container.