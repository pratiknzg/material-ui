---
title: React 菜单组件
components: Menu, MenuItem, MenuList, ClickAwayListener, Popover, Popper
---
# 菜单

<p class="description">菜单显示在临时出现的所点击位置上的选项列表。</p>

[菜单](https://material.io/design/components/menus.html)通过一个临时出现的界面来显示选项列表。通常当用户与按钮，操作或其他控件交互时出现。

## 基本菜单

默认情况下, 基本菜单会在锚点元素上打开 (此选项可通过props更改)。当靠近屏幕边缘时, 简单菜单会垂直调整以使所有菜单项完全可见。

选择一个选项后, 最好立即提交该选项并关闭菜单。

**解疑**: 与基本菜单相比, 基本对话框可以显示与列表项可用选项相关的其他详细信息, 或者提供与主要任务相关的导航类的或垂直的操作。 虽然它们可以显示相同的内容, 但基本菜单比基本对话框更可取, 因为基本菜单对用户当前上下文的破坏性较小。

{{"demo": "pages/demos/menus/SimpleMenu.js"}}

## 选择菜单

如果用于项目选择, 则在打开时, 基本菜单会尝试将当前选定的菜单项与定位元素垂直对齐。 使用` selected `属性将菜单项设置为当前选中（从[ListItem](/api/list-item/))。

{{"demo": "pages/demos/menus/SimpleListMenu.js"}}

如果基本菜单中的文本一行无法显示完，则使用基本对话框来代替。基本对话框可以有不同高度的行。

## 限高菜单

如果菜单的最大高度仍无法显示所有菜单项，则菜单可以在内部滚动。

{{"demo": "pages/demos/menus/LongMenu.js"}}

## MenuList 组件

`Menu`组件内部使用`Popver`组件 但是，您可能想药使用不同的定位策略，或者你不想禁止滚动。 为了满足这些需求，我们公开了一个`MenuList`组件，让你可以像下面例子中这样组合`Popper`来编写自己的菜单组件。

`MenuList`组件的主要职责是处理焦点。

{{"demo": "pages/demos/menus/MenuListComposition.js"}}

## 定制菜单项

`MenuItem`实际上是在`ListItem`之上增加了一些样式的封装。 所以你可以靠`MenuItem`来使用相同的列表组合特性：

{{"demo": "pages/demos/menus/ListItemComposition.js"}}

## 更改过渡动画

使用不同的过渡动画。

{{"demo": "pages/demos/menus/FadeMenu.js"}}

## Render Props

这是[render props](https://reactjs.org/docs/render-props.html) 的例子。保持跟踪单个菜单的本地状态。

{{"demo": "pages/demos/menus/RenderPropsMenu.js"}}

## 局限性

There is [a flexbox bug](https://bugs.chromium.org/p/chromium/issues/detail?id=327437) that prevents `text-overflow: ellipse` from working in a flexbox layout. You can use the `Typography` component to workaround this issue:

{{"demo": "pages/demos/menus/TypographyMenu.js"}}

## Complementary projects

For more advanced use cases you might be able to take advantage of:

### PopupState helper

There is a 3rd party package [`material-ui-popup-state`](https://github.com/jcoreio/material-ui-popup-state) that takes care of menu state for you in most cases.

{{"demo": "pages/demos/menus/MenuPopupState.js"}}