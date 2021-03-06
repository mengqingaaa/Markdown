# 自动转义

*自动转义* 是指自动对*特殊字符*进行转义。  
*特殊字符* 是指HTML（或XML和XHTML）中的 `&`、`<`、`>`、`"`和`'`。  
因为特殊字符代表了特殊的意思，所以如果要在文本中使用它们就必须把它们替换为**“实体”**。  
如果不转义，那么用户就无法使用这些字符，而且还会带来安全问题。

### `flask.config.from_object()`
`from_object()` 会查看给定的独享（如果该对象使一个字符串就会直接导入它），
搜索对象中所有变量名均为**大写字母**的变量。