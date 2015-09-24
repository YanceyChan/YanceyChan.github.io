---
layout: post
title: "Use of undectared identifier '_xxxx'"
date: 2015-09-24 16:51:18 +0800
comments: true
categories: error

---
今天自定义一个继承UITextField的textField的时候，设置变量_borderColor的setter和getter方法的时候，出现了这样的报错

```
#import <UIKit/UIKit.h>
IB_DESIGNABLE
@interface CYSTextField : UITextField
@property (strong, nonatomic) IBInspectable UIColor *borderColor;
@property (assign, nonatomic) IBInspectable CGFloat borderWidth;
@property (assign, nonatomic) IBInspectable CGFloat cornerRaduis;
@end
```

单独设置setter方法的时候没有问题，但是加上getter方法的时候，xcode就会提示undectared identifier '_xxxx'这样的错误了。

```
- (UIColor *)borderColor{
    
    if (!_borderColor) {
        return [UIColor blueColor];
    }
    return _borderColor;
}

- (void)setBorderColor:(UIColor *)borderColor{
    _borderColor = borderColor;
    self.layer.borderColor = _borderColor.CGColor;
}
```
在上面加上
`@synthesize borderColor = _borderColor;`
后，问题就解决了。

度娘了一下，问题出现的原因应该是_borderColor 是变量，borderColor是属性。borderColor属性生成存取方法是setBorderColor和borderColor，这2个方法操作的变量是_borderColor

getter器的方法名直接就是变量名，方法名和变量名一样，容易让人迷糊，所以，可以这样优化
这样我们就去使用_xxxxx，像使用xxxxx一样。