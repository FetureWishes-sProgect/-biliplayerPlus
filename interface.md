# TampermonkeyTool接口文档

## 数据字段

| 字段名 | 接受数据类型 | 默认值 | 字段注释 |
|  ----  | ----  | ---- | ---- |
| settingName | string | "tampermonkeyTool默认设置" | 用于设置脚本的名字，会在设置窗口顶部显示，并且会注册到tampermonkey的菜单项中 |
| elementMapper | array | 略 | 元素映射表 |
| default | object | 略 | 默认设置，接下来会通过mixin函数将config合并进来 |
| config | array | GM_listValues() | 保存的设置，从GM本地存储的数据list |
| maxInitTimes | number | 6 | 最大初始化次数 |
| keyboardBindList | object | { } | 已用按键列表，用于存储快捷键的映射表 |
| touchList | object | { } | 触屏按下的手指列表 |
| coreVersion | string | 随版本号而定 | 内核版本，即TampermonkeyTool的版本 |

## 方法字段

| 字段名 | 参数 | 默认参数 | 功能 |
|  ----  | ----  | ---- | ---- |
| getElementMapper |  |  | 用于获取所有的元素映射表 |
| getSettingRootElement |  |  | 获取跟元素节点（设置面板会挂载的节点），elementMapper中的settingRootElement字段 |
| watchValue | value:监听的元素，key:监听的值 |  | 监听指定元素key的变化 |
| scrollThrottle | fn:需要节流的函数,wait:最短触发时间 |  | 滚动节流函数 |
| createMapperTarget | key |  | 给gridListSettingMapper中的元素进行target创建 |
| mapperAddDependency | target:添加依赖的目标, dependency:添加的依赖 |  | 给gridListSettingMapper的元素添加依赖 |
| settingPanelReload |  |  | 重新加载设置面板 |
| switchSettingPanel |  |  | 切换设置面板的显隐状态 |
| keyHandler | key |  | 执行对应按键的功能 |
| getShortcutKeyName | keyboard |  | 根据快捷键字符串，获取按键对应的功能名 |
| bindKeyBoardListener |  |  | 监听全局的键盘事件，以触发快捷键 |
| messageShow | message,displayTime=2000 |  | 提示信息显示 |
| valueChangeHandler | key |  | 当key值发生改变时，用以通知页面改变 |
| saveValue | key |  | 保存配置 |
| touchHandler | element,func |  | 触发对应的触摸函数 |
| touchFunRunner | isshow |  | 不是展示状态则代表直接执行，执行函数 |
| mixin |  |  | 混入设置，将default和config合并 |
| versionUpdateHandler | oldVersion, newVersion |  | 控制用户脚本所有版本的更新逻辑，用于更改不同版本的配置结构 |
| coreUpdateHandler | oldVersion, newVersion |  | 控制tampermonkey所有版本的更新逻辑，用于更改不同版本的配置结构 |
| versionUpdater |  |  | 检测脚本、内核的版本，进行升级，触发对应的升级handler |
| resetSetting |  |  | 重置设置 |
| listenHistoryChange |  |  | 监听浏览器历史记录的变化，防止挂载丢失 |
| preInit |  |  | 预初始化 |
| init |  |  | 初始化 |
| main |  |  | 主函数 |

## 元素组件构造函数

| 字段名 | 参数 | 默认参数 | 功能 |
|  ----  | ----  | ---- | ---- |
| createSwitch |  |  | 用于创建开关 |
| createCheckBox |  |  | 用于创建多选框 |
| createButton |  |  | 用于创建按钮 |
| createIcon |  |  | 用于创建图标 |
| createProcessBar |  |  | 用于创建进度条 |
| createSelect |  |  | 用于创建下拉框 |
| createNumberBox |  |  | 用于创建数字输入 |
| registerToolTip |  |  | 用于注册气泡通知组件 |
| createSettingPanel |  |  | 用于创建设置面板 |


