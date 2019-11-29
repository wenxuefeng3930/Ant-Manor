<!--
 * @Author: TonyJiangWJ
 * @Date: 2019-11-27 09:31:06
 * @Last Modified by: TonyJiangWJ
 * @Last Modified time: 2019-11-29 17:42:22
 * @Description: 
 -->
### 蚂蚁庄园自动喂鸡驱赶脚本
- 基于AutoJS实现的自动喂养脚本
- 自动解锁需要在config.js中修改password值 最好是pin密码 其他密码不保证完全有效
  ```javascript
  var default_config = {
  password: '',
  ```
- 运行完毕后程序会通过手势自动关闭支付宝，但是仅仅支持MIUI全面屏手势 其他手机可以自行编写 否则程序仅仅返回
  ```
  /**
   * 杀死当前APP 仅适用于MIUI10+ 全面屏手势操作
   */
  this.killCurrentApp = function () {
    if (config.killAppWithGesture) {
      recents()
      sleep(1000)
      gesture(320, [240, 1000], [800, 1000])
      sleep(400)
      home()
    }
  }

  // config中配置开关
  let no_gui_config = {
    //....
    // 完成后通过手势kill支付宝应用，目前只支持MIUI全面屏手势 默认关闭
    killAppWithGesture: false
  }
  ```
- `星星球`脚本，打开AutoJS悬浮球 然后进入到开始的界面，通过悬浮球菜单打开`星星球.js` 自动开始和小鸡玩，默认达到230分就结束。
- `小鸡登山`脚本正在开发中。。。目前没法正式使用