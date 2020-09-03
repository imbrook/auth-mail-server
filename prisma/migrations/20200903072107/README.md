# Migration `20200903072107`

This migration has been generated by brook-im at 9/3/2020, 4:21:07 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
ALTER TABLE `auth-mail`.`User` DROP COLUMN `keyForVerify`,
ADD COLUMN `isAuthenticated` boolean  NOT NULL DEFAULT false
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration 20200903062240..20200903072107
--- datamodel.dml
+++ datamodel.dml
@@ -1,15 +1,15 @@
 datasource db {
   provider = "mysql"
-  url = "***"
+  url = "***"
 }
 generator client {
   provider = "prisma-client-js"
 }
 model User {
-  id           String @default(cuid()) @id
-  email        String
-  keyForVerify String?
+  id              String  @default(cuid()) @id
+  email           String
+  isAuthenticated Boolean @default(false)
 }
```

