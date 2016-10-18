# Video_SDK_iOS

Domob视频SDKSDK包的内容如下: 

1.IndependentVideoSDK:
* 包含 Domob iOS 视频积分墙 SDK 库文件、头文件以及相关支持文件

2.IndependentVideoSample:示例工程(含有IndependentVideoSDK)。
* 为了在运行示例工程时能出广告,请从多盟视频官网（http://dvx.domob.cn) 的获取您的Publisher ID替换Samples中的ID。

3.SDKUserGuide.pdf
* Domob iOS 视频 SDK 的用户指南文档

![image](https://github.com/domobVideoSDK/Video_SDK_iOS/blob/master/images/lib.png)

```java  
  
#import "IndependentVideoManager.h"

@interface ViewController: UIViewController<IndependentVideoManagerDelegate> {
    IndependentVideoManager *_manager;
}

@implementation ViewController

- (void)viewDidLoad
{
    [super viewDidLoad];
    // 设置实现了IndependentVideoManagerDelegate协议的对象，一般为self。
    _manager = [[IndependentVideoManager alloc] initWithPublisherID:@"申请的publishId" andUserID:nil];
    _manager.delegate = self;
}


// 通过实现IndependentVideoManagerDelegate中定义的方法，来跟踪视频生命周期的各个阶段。所有这些方法也都定义在IndependentVideoManager.h中，如下：
#pragma mark - video present callback 视频展现回调
// 开始加载数据。
- (void)ivManagerDidStartLoad:(IndependentVideoManager *)manager;

// 加载完成。
- (void)ivManagerDidFinishLoad:(IndependentVideoManager *)manager fin-ished:(BOOL)isFinished;

// 加载失败，可能的原因由error提供，如网络连接失败、被禁用等。
- (void)ivManager:(IndependentVideoManager *)manager
failedLoadWithError:(NSError *)error;

// 当视频要被呈现出来时，回调该方法
- (void)ivManagerWillPresent:(IndependentVideoManager *)manager

// 视频播放完成.
- (void)ivManagerCompletePlayVideo:(IndependentVideoManager *)manager;

// 播放视频失败
- (void)ivManagerPlayIndependentVideo:(IndependentVideoManager *)manager
                            withError:(NSError *)error

// 当视频被关闭。
- (void)ivManagerDidClosed:(IndependentVideoManager *)manager

// 检查视频状态的回调
- (void)ivManager:(IndependentVideoManager *)manager
isIndependentVideoAvailable:(BOOL)available


// 检查是否有视频广告可以播放：
- (IBAction)checkVideoAvailable {
    
    [_manager checkVideoAvailable];
    
}

// 设置是否在播放完成后弹出弹框,默认为NO,为弹出：
_manager.disableShowAlert = YES;

  
```


##DOMOB iOS independent video sdk changelog

###3.3.4&emsp;&emsp;2016/10/17

1.优化iOS10系统下获取idfa为0值时无视频的弹窗提示

=================================
###3.3.3  2016/09/22

1.新增竖屏/倒竖屏游戏适配

2.bug fix 

=================================
###3.3.2  2016/09/06

1.fix无网络状态播放视频的bug

=================================
###3.3.1  2016/08/12

1.bug fix

=================================
###3.3.0  2016/07/22

1.bug fix

2.点击关闭按钮跳转landingPage,landingPage的横竖屏适配

3.新增实时检测视频状态功能

_________________________________________

###3.2.0  2016/06/15

1.去掉加载视图界面 

2.去掉非wifi下播放视频时让用户确认的提示框。

3.修改展示视频的业务逻辑

4.bug fix

_________________________________________

###3.1.1  2016/06/05

1.bug fix
2.去掉获取用户location信息

_________________________________________

###3.1.0  2016/01/19

1.加载界面视觉优化 

2.性能优化 

3.弹窗场景优化 

4.bug fix

_________________________________________

###3.0.0  2015/12/29

1.预加载优化

2.增加播放器的静音功能 

3.弹窗样式更新 

4.弹窗文案优化 

5.bug fix

_________________________________________

###2.2.0  2015/08/05

1.弹框样式改变 

2.播放完成后的弹框可控 

3.bug fix

_________________________________________

###2.1.0  2015/04/13

1.预加载优化

2.转化率提升优化

3.bug fix

_________________________________________


###2.0.0  2015/02/05


1.模板优化
_________________________________________


###1.3.2  2015/01/19


1.增加视频完成播放的回调
_________________________________________


###1.3.1  2015/01/09


1.bug fix
_________________________________________


###1.3.0  2014/12/03


1.更新SDK使用接口
_________________________________________


###1.2.3


1.成功获取积分回调接口中添加本次视频获得的积分数
_________________________________________


###1.2.2


1.bug fix
_________________________________________


###1.2.1


1.修复在iOS8上的兼容性问题
_________________________________________


###1.2.0
1.增加iai支持
_________________________________________


###1.1.0


1.添加检测是否有可以播放的视频广告接口 
2.修复loading过长问题
_________________________________________


###1.0.0  2014
原始版本
--------------------------
