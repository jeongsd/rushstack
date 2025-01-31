## API Report File for "@rushstack/heft-config-file"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

import { RigConfig } from '@rushstack/rig-package';
import { Terminal } from '@rushstack/node-core-library';

// @beta (undocumented)
export class ConfigurationFile<TConfigurationFile> {
    constructor(options: IConfigurationFileOptions<TConfigurationFile>);
    // @internal (undocumented)
    static _formatPathForLogging: (path: string) => string;
    getObjectSourceFilePath<TObject extends object>(obj: TObject): string | undefined;
    getPropertyOriginalValue<TParentProperty extends object, TValue>(options: IOriginalValueOptions<TParentProperty>): TValue | undefined;
    loadConfigurationFileForProjectAsync(terminal: Terminal, projectPath: string, rigConfig?: RigConfig): Promise<TConfigurationFile>;
    readonly projectRelativeFilePath: string;
    tryLoadConfigurationFileForProjectAsync(terminal: Terminal, projectPath: string, rigConfig?: RigConfig): Promise<TConfigurationFile | undefined>;
    }

// @beta (undocumented)
export interface IConfigurationFileOptions<TConfigurationFile> {
    jsonPathMetadata?: IJsonPathsMetadata;
    jsonSchemaPath: string;
    projectRelativeFilePath: string;
    propertyInheritance?: IPropertiesInheritance<TConfigurationFile>;
}

// @beta (undocumented)
export interface ICustomPropertyInheritance<TObject> extends IPropertyInheritance<InheritanceType.custom> {
    inheritanceFunction: PropertyInheritanceCustomFunction<TObject>;
}

// @beta
export interface IJsonPathMetadata {
    pathResolutionMethod?: PathResolutionMethod;
}

// @beta
export interface IJsonPathsMetadata {
    // (undocumented)
    [jsonPath: string]: IJsonPathMetadata;
}

// @beta (undocumented)
export enum InheritanceType {
    append = "append",
    custom = "custom",
    replace = "replace"
}

// @beta (undocumented)
export interface IOriginalValueOptions<TParentProperty> {
    // (undocumented)
    parentObject: TParentProperty;
    // (undocumented)
    propertyName: keyof TParentProperty;
}

// @beta (undocumented)
export type IPropertiesInheritance<TConfigurationFile> = {
    [propertyName in keyof TConfigurationFile]?: IPropertyInheritance<InheritanceType.append | InheritanceType.replace> | ICustomPropertyInheritance<TConfigurationFile[propertyName]>;
};

// @beta (undocumented)
export interface IPropertyInheritance<TInheritanceType extends InheritanceType> {
    // (undocumented)
    inheritanceType: TInheritanceType;
}

// @beta (undocumented)
export enum PathResolutionMethod {
    NodeResolve = 2,
    resolvePathRelativeToConfigurationFile = 0,
    resolvePathRelativeToProjectRoot = 1
}

// @beta (undocumented)
export type PropertyInheritanceCustomFunction<TObject> = (currentObject: TObject, parentObject: TObject) => TObject;


// (No @packageDocumentation comment for this package)

```
