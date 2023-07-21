# Prisma Pagination Extension

[![Version](http://img.shields.io/npm/v/prisma-pagination.svg)](https://npmjs.org/package/prisma-pagination-extension)
[![License](https://img.shields.io/npm/l/prisma-pagination.svg)](https://npmjs.org/package/prisma-pagination-extension)

## Introduction

Prisma Client extension for pagination.

## Installation

```bash
npm i prisma-pagination-extension
```

## Usage

```typescript
import { PrismaClient } from "@prisma/client";
import paginationExtension from 'prisma-pagination-extension';

const prisma = new PrismaClient();

const xprisma = prisma.$extends(paginationExtension);

const [users, meta] = await xprisma.user.paginate({
    select: {
        firstName: true,
        lastName: true,
        email: true,
    },
    pagination: {
        page: 1,
        pageSize: 10,
    },
});

/* meta structure:
{
    page: number
    pageSize: number
    pageCount: number
    total: number
}
*/
```

## License
[MIT](https://choosealicense.com/licenses/mit/)
