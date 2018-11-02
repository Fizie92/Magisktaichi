## 为何模块提示未激活？

如果 Xposed 没有被太极重新创建，那么模块所需要的 Xposed 运行环境并不存在；因此会出现未激活。要解决这问题，需要把模块在 太极 中重新创建。**但是不推荐这么做**。模块需要加载，其实本身并不需要Xposed 环境；只要模块不做出“发现模块没有激活，就完全不给使用的逻辑”，一般情况下是没有任何问题的。

## 如何判断模块是否激活了？

接上条；我们不推荐把 Xposed 模块重新创建。但是如果需要查询用户是否勾选了你这么模块，这样是可以的；直接copy如下代码判断即可：

```java
    public static boolean isModuleActive(Context context) {
        if (context == null) {
            throw new IllegalArgumentException("context must not be null!!");
        }

        ContentResolver contentResolver = context.getContentResolver();
        if (contentResolver == null) {
            return false;
        }

        Uri uri = Uri.parse("content://me.weishu.exposed.CP/");
        Bundle result = contentResolver.call(uri, "active", null, null);
        if (result == null) {
            return false;
        }

        return result.getBoolean("active", false);
    }
```