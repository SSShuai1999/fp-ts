---
title: Separated.ts
nav_order: 73
parent: Modules
---

## Separated overview

Added in v3.0.0

---

<h2 class="text-delta">Table of contents</h2>

- [Bifunctor](#bifunctor)
  - [bimap](#bimap)
  - [mapLeft](#mapleft)
- [Functor](#functor)
  - [map](#map)
- [constructors](#constructors)
  - [separated](#separated)
- [instances](#instances)
  - [Bifunctor](#bifunctor-1)
  - [Functor](#functor-1)
  - [URI (type alias)](#uri-type-alias)
- [utils](#utils)
  - [Separated (interface)](#separated-interface)
  - [left](#left)
  - [right](#right)

---

# Bifunctor

## bimap

Map a pair of functions over the two type arguments of the bifunctor.

**Signature**

```ts
export declare const bimap: <E, G, A, B>(f: (e: E) => G, g: (a: A) => B) => (fea: Separated<E, A>) => Separated<G, B>
```

Added in v3.0.0

## mapLeft

Map a function over the first type argument of a bifunctor.

**Signature**

```ts
export declare const mapLeft: <E, G>(f: (e: E) => G) => <A>(fea: Separated<E, A>) => Separated<G, A>
```

Added in v3.0.0

# Functor

## map

`map` can be used to turn functions `(a: A) => B` into functions `(fa: F<A>) => F<B>` whose argument and return types
use the type constructor `F` to represent some computational context.

**Signature**

```ts
export declare const map: <A, B>(f: (a: A) => B) => <E>(fa: Separated<E, A>) => Separated<E, B>
```

Added in v3.0.0

# constructors

## separated

**Signature**

```ts
export declare const separated: <E, A>(left: E, right: A) => Separated<E, A>
```

Added in v3.0.0

# instances

## Bifunctor

**Signature**

```ts
export declare const Bifunctor: Bifunctor2<'Separated'>
```

Added in v3.0.0

## Functor

**Signature**

```ts
export declare const Functor: Functor2<'Separated'>
```

Added in v3.0.0

## URI (type alias)

**Signature**

```ts
export type URI = 'Separated'
```

Added in v3.0.0

# utils

## Separated (interface)

**Signature**

```ts
export interface Separated<E, A> {
  readonly left: E
  readonly right: A
}
```

Added in v3.0.0

## left

**Signature**

```ts
export declare const left: <E, A>(s: Separated<E, A>) => E
```

Added in v3.0.0

## right

**Signature**

```ts
export declare const right: <E, A>(s: Separated<E, A>) => A
```

Added in v3.0.0