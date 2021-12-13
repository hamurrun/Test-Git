税号：taxpayerIdRegex = /^[A-Z0-9]{15}$|^[A-Z0-9]{17}$|^[A-Z0-9]{18}$|^[A-Z0-9]{20}$/

邮箱：emailRegex = /^[0-9a-zA-Z\u4e00-\u9fa5_\.-]+@[0-9a-zA-Z_-]+(\.[0-9a-zA-Z_-]+)+$/

手机号：mobileRegex = /^1[2|3|4|5|6|7|8|9][0-9]{9}$/

身份证：regExp = /^(?:[\dXx]{15})(?:[\dXx]{3})?$/

称呼：regExp = !/^[^0-9 ]{2,30}$/.test(value) // 中文，英文， 符号 （除去数字和空格）

callRegExp: /^[\u4E00-\u9FA5A-Za-z_@#*&^$+~. ]{5,8}$/, // 称呼--中文 英文 符号 空格

phoneRegExp: /^[^A-Za-z0-9 ]{11}$/ // 称呼--中文 英文 符号

regExp.test(‘检测项’）