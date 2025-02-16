---
title: BCP036
description: Error/warning - The property <property-name> expected a value of type <data-type> but the provided value is of type <data-type>.
ms.topic: reference
ms.custom: devx-track-bicep
ms.date: 07/15/2024
---

# Bicep error/warning code - BCP036

This error/warning occurs when you assign a value to a property whose expected data type is not compatible with that of the assigned value.

## Error/warning description

`The property <property-name> expected a value of type <data-type> but the provided value is of type <data-type>.`

## Solution

Assign a value with the correct data type.

## Examples

The following example raises the error because `sku` is defined as a string, not an integer:

```bicep
type storageAccountConfigType = {
  name: string
  sku: string
}

param foo storageAccountConfigType = {
  name: 'myStorage'
  sku: 2
}
```

You can fix the issue by assigning a string value to `sku`:

```bicep
type storageAccountConfigType = {
  name: string
  sku: string
}

param foo storageAccountConfigType = {
  name: 'myStorage'
  sku: 'Standard_LRS' 
}
```

## Next steps

For more information about Bicep error and warning codes, see [Bicep warnings and errors](./bicep-error-codes.md).
