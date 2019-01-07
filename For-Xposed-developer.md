## 为何模块提示未激活？

如果 Xposed 没有被太极重新创建，那么模块所需要的 Xposed 运行环境并不存在；因此会出现未激活。要解决这问题，需要把模块在 太极 中重新创建。**但是不推荐这么做**。模块需要加载，其实本身并不需要Xposed 环境；只要模块不做出“发现模块没有激活，就完全不给使用的逻辑”，一般情况下是没有任何问题的。

## 如何判断模块是否激活了？

接上条；我们不推荐把 Xposed 模块重新创建。但是如果需要查询用户是否勾选了你这么模块，这样是可以的；直接copy如下代码判断即可：

```java
    private static boolean isExpModuleActive(Context context) {

        boolean isExp = false;
        if (context == null) {
            throw new IllegalArgumentException("context must not be null!!");
        }

        try {
            ContentResolver contentResolver = context.getContentResolver();
            Uri uri = Uri.parse("content://me.weishu.exposed.CP/");
            Bundle result = contentResolver.call(uri, "active", null, null);
            if (result == null) {
                return false;
            }
            isExp = result.getBoolean("active", false);
        } catch (Throwable ignored) {
        }
        return isExp;
    }
```

## 如何判断 Exp 创建了哪些应用？

在某些情况下，我们需要处理应用列表。比如说，权限管理模块，可能用户只需要对特定的应用进行权限管理。因此，模块中需要列出所有应用，让用户选择。

但是在 EXposed 中，并非所有APP都能加载Xposed模块。**只有EXposed创建过的模块才能使用Xposed 功能**。因此，需要有办法知道EXposed 中的APP列表。可以用如下方法获取：

```java
    private static List<String> getExpApps(Context context) {
        Bundle result;
        try {
            result = context.getContentResolver().call(Uri.parse("content://me.weishu.exposed.CP/"), "apps", null, null);
        } catch (Throwable e) {
            return Collections.emptyList();
        }

        if (result == null) {
            return Collections.emptyList();
        }
        List<String> list = result.getStringArrayList("apps");
        if (list == null) {
            return Collections.emptyList();
        }
        return list;
    }
```