---
id: FieldApi
title: FieldApi
---

# Class: FieldApi\<TParentData, TName, TFieldValidator, TFormValidator, TData\>

A class representing the API for managing a form field.

Normally, you will not need to create a new `FieldApi` instance directly.
Instead, you will use a framework hook/function like `useField` or `createField`
to create a new instance for you that uses your framework's reactivity model.
However, if you need to create a new instance manually, you can do so by calling
the `new FieldApi` constructor.

## Type Parameters

• **TParentData**

• **TName** *extends* [`DeepKeys`](../type-aliases/deepkeys.md)\<`TParentData`\>

• **TFieldValidator** *extends* `Validator`\<[`DeepValue`](../type-aliases/deepvalue.md)\<`TParentData`, `TName`\>, `unknown`\> \| `undefined` = `undefined`

• **TFormValidator** *extends* `Validator`\<`TParentData`, `unknown`\> \| `undefined` = `undefined`

• **TData** *extends* [`DeepValue`](../type-aliases/deepvalue.md)\<`TParentData`, `TName`\> = [`DeepValue`](../type-aliases/deepvalue.md)\<`TParentData`, `TName`\>

## Constructors

### new FieldApi()

```ts
new FieldApi<TParentData, TName, TFieldValidator, TFormValidator, TData>(opts): FieldApi<TParentData, TName, TFieldValidator, TFormValidator, TData>
```

Initializes a new `FieldApi` instance.

#### Parameters

##### opts

[`FieldApiOptions`](../interfaces/fieldapioptions.md)\<`TParentData`, `TName`, `TFieldValidator`, `TFormValidator`, `TData`\>

#### Returns

[`FieldApi`](fieldapi.md)\<`TParentData`, `TName`, `TFieldValidator`, `TFormValidator`, `TData`\>

#### Defined in

[packages/form-core/src/FieldApi.ts:474](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L474)

## Properties

### form

```ts
form: FormApi<TParentData, TFormValidator>;
```

A reference to the form API instance.

#### Defined in

[packages/form-core/src/FieldApi.ts:436](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L436)

***

### name

```ts
name: unknown extends TParentData ? string : TParentData extends readonly any[] & IsTuple<TParentData> ? PrefixTupleAccessor<TParentData<TParentData>, AllowedIndexes<TParentData<TParentData>, never>, []> : TParentData extends any[] ? PrefixArrayAccessor<TParentData<TParentData>, [any]> : TParentData extends Date ? never : TParentData extends object ? PrefixObjectAccessor<TParentData<TParentData>, []> : TParentData extends string | number | bigint | boolean ? "" : never;
```

The field name.

#### Defined in

[packages/form-core/src/FieldApi.ts:446](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L446)

***

### options

```ts
options: FieldApiOptions<TParentData, TName, TFieldValidator, TFormValidator, TData>;
```

The field options.

#### Defined in

[packages/form-core/src/FieldApi.ts:450](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L450)

***

### state

```ts
state: FieldState<TData>;
```

The current field state.

#### Defined in

[packages/form-core/src/FieldApi.ts:464](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L464)

***

### store

```ts
store: Store<FieldState<TData>, (cb) => FieldState<TData>>;
```

The field state store.

#### Defined in

[packages/form-core/src/FieldApi.ts:460](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L460)

***

### timeoutIds

```ts
timeoutIds: Record<ValidationCause, null | Timeout>;
```

#### Defined in

[packages/form-core/src/FieldApi.ts:469](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L469)

## Methods

### getInfo()

```ts
getInfo(): FieldInfo<TParentData, TFormValidator>
```

Gets the field information object.

#### Returns

[`FieldInfo`](../type-aliases/fieldinfo.md)\<`TParentData`, `TFormValidator`\>

#### Defined in

[packages/form-core/src/FieldApi.ts:713](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L713)

***

### getMeta()

```ts
getMeta(): FieldMeta
```

Gets the current field metadata.

#### Returns

[`FieldMeta`](../type-aliases/fieldmeta.md)

#### Defined in

[packages/form-core/src/FieldApi.ts:691](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L691)

***

### ~~getValue()~~

```ts
getValue(): TData
```

Gets the current field value.

#### Returns

`TData`

#### Deprecated

Use `field.state.value` instead.

#### Defined in

[packages/form-core/src/FieldApi.ts:665](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L665)

***

### handleBlur()

```ts
handleBlur(): void
```

Handles the blur event.

#### Returns

`void`

#### Defined in

[packages/form-core/src/FieldApi.ts:1065](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L1065)

***

### handleChange()

```ts
handleChange(updater): void
```

Handles the change event.

#### Parameters

##### updater

[`Updater`](../type-aliases/updater.md)\<`TData`\>

#### Returns

`void`

#### Defined in

[packages/form-core/src/FieldApi.ts:1058](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L1058)

***

### insertValue()

```ts
insertValue(
   index, 
   value, 
opts?): Promise<void>
```

Inserts a value at the specified index, shifting the subsequent values to the right.

#### Parameters

##### index

`number`

##### value

`TData` *extends* `any`[] ? `TData`\<`TData`\>\[`number`\] : `never`

##### opts?

`UpdateMetaOptions`

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/form-core/src/FieldApi.ts:726](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L726)

***

### mount()

```ts
mount(): () => void
```

Mounts the field instance to the form.

#### Returns

`Function`

##### Returns

`void`

#### Defined in

[packages/form-core/src/FieldApi.ts:575](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L575)

***

### moveValue()

```ts
moveValue(
   aIndex, 
   bIndex, 
   opts?): void
```

Moves the value at the first specified index to the second specified index.

#### Parameters

##### aIndex

`number`

##### bIndex

`number`

##### opts?

`UpdateMetaOptions`

#### Returns

`void`

#### Defined in

[packages/form-core/src/FieldApi.ts:756](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L756)

***

### pushValue()

```ts
pushValue(value, opts?): void
```

Pushes a new value to the field.

#### Parameters

##### value

`TData` *extends* `any`[] ? `TData`\<`TData`\>\[`number`\] : `never`

##### opts?

`UpdateMetaOptions`

#### Returns

`void`

#### Defined in

[packages/form-core/src/FieldApi.ts:718](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L718)

***

### removeValue()

```ts
removeValue(index, opts?): Promise<void>
```

Removes a value at the specified index.

#### Parameters

##### index

`number`

##### opts?

`UpdateMetaOptions`

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/form-core/src/FieldApi.ts:744](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L744)

***

### replaceValue()

```ts
replaceValue(
   index, 
   value, 
opts?): Promise<void>
```

Replaces a value at the specified index.

#### Parameters

##### index

`number`

##### value

`TData` *extends* `any`[] ? `TData`\<`TData`\>\[`number`\] : `never`

##### opts?

`UpdateMetaOptions`

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/form-core/src/FieldApi.ts:735](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L735)

***

### setErrorMap()

```ts
setErrorMap(errorMap): void
```

Updates the field's errorMap

#### Parameters

##### errorMap

`ValidationErrorMap`

#### Returns

`void`

#### Defined in

[packages/form-core/src/FieldApi.ts:1085](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L1085)

***

### setMeta()

```ts
setMeta(updater): void
```

Sets the field metadata.

#### Parameters

##### updater

[`Updater`](../type-aliases/updater.md)\<[`FieldMeta`](../type-aliases/fieldmeta.md)\>

#### Returns

`void`

#### Defined in

[packages/form-core/src/FieldApi.ts:707](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L707)

***

### setValue()

```ts
setValue(updater, options?): void
```

Sets the field value and run the `change` validator.

#### Parameters

##### updater

[`Updater`](../type-aliases/updater.md)\<`TData`\>

##### options?

`UpdateMetaOptions`

#### Returns

`void`

#### Defined in

[packages/form-core/src/FieldApi.ts:672](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L672)

***

### swapValues()

```ts
swapValues(
   aIndex, 
   bIndex, 
   opts?): void
```

Swaps the values at the specified indices.

#### Parameters

##### aIndex

`number`

##### bIndex

`number`

##### opts?

`UpdateMetaOptions`

#### Returns

`void`

#### Defined in

[packages/form-core/src/FieldApi.ts:750](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L750)

***

### update()

```ts
update(opts): void
```

Updates the field instance with new options.

#### Parameters

##### opts

[`FieldApiOptions`](../interfaces/fieldapioptions.md)\<`TParentData`, `TName`, `TFieldValidator`, `TFormValidator`, `TData`\>

#### Returns

`void`

#### Defined in

[packages/form-core/src/FieldApi.ts:628](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L628)

***

### validate()

```ts
validate(cause): ValidationError[] | Promise<ValidationError[]>
```

Validates the field value.

#### Parameters

##### cause

`ValidationCause`

#### Returns

[`ValidationError`](../type-aliases/validationerror.md)[] \| `Promise`\<[`ValidationError`](../type-aliases/validationerror.md)[]\>

#### Defined in

[packages/form-core/src/FieldApi.ts:1030](https://github.com/TanStack/form/blob/main/packages/form-core/src/FieldApi.ts#L1030)
