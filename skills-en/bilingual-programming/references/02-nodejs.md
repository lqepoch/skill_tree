# Node.js / TypeScript Bilingual Guide

## EN: Overview

TypeScript uses JSDoc style. `/** */` above declarations, `//` for inline.

## CN: 概述

TypeScript 使用 JSDoc 风格。`/** */` 在声明上方，`//` 用于行内。

---

## Function

```typescript
/**
 * EN: Returns the maximum of two values.
 * CN: 返回两个值中的最大值。
 *
 * @param a
 *        EN: First value.
 *        CN: 第一个值。
 * @param b
 *        EN: Second value.
 *        CN: 第二个值。
 * @returns
 *        EN: Maximum value.
 *        CN: 最大值。
 *
 * @example
 *         EN: max(1, 2) // returns 2
 *         CN: max(1, 2) // 返回 2
 */
export function max<T extends number>(a: T, b: T): T {
    return a > b ? a : b;
}
```

---

## Interface

```typescript
/**
 * EN: Generic key-value configuration.
 * CN: 通用键值配置。
 *
 * @usage
 *        EN: Use for app settings.
 *        CN: 用于应用设置。
 */
export interface Config {
    /**
     * EN: Configuration key.
     * CN: 配置键。
     */
    key: string;

    /**
     * EN: Configuration value.
     * CN: 配置值。
     */
    value: unknown;
}
```

---

## Type

```typescript
/**
 * EN: Operation result with status.
 * CN: 带状态的操作结果。
 *
 * @template T
 *        EN: Value type.
 *        CN: 值类型。
 */
export type Result<T> =
    | { success: true; value: T }
    | { success: false; error: Error };
```

---

## Inline

```typescript
// EN: Guard against undefined.
// CN: 防御 undefined。
if (value === undefined) return;

// EN: Use nullish coalescing.
// CN: 使用空值合并。
const count = data.count ?? 0;
```

---

## Naming

| Type | Style | Example |
|------|-------|---------|
| Function | camelCase | `max` |
| Class | PascalCase | `ConfigManager` |
| Interface | PascalCase | `Config` |
| Constant | SCREAMING_SNAKE | `MAX_RETRIES` |
| Type | PascalCase | `Result` |
