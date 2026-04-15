# Frontend Code Style (Vue3)

## 1. 核心语法原则
- **强制使用组合式 API**：必须使用 Vue 3 的 `<script setup>` 语法糖。
- **禁止降级**：严禁在代码中混合使用 Vue 2 的 Options API（如 `data()`, `methods`, `computed: {}`）。

## 2. 状态与逻辑隔离
- **响应式定义**：基本类型使用 `ref`，复杂对象使用 `reactive`。
- **逻辑复用**：当组件内包含复杂的独立业务逻辑（如表单校验、复杂计算）时，必须抽离为独立的 `useXxx` (Composable) 函数，不要把所有逻辑堆砌在同一个文件中。

## 3. 命名约定
- **组件文件**：使用 PascalCase（大驼峰），如 `UserProfile.vue`。
- **变量与函数**：使用 camelCase（小驼峰），如 `fetchUserData`。
- **事件发射**：`emit` 事件名使用 kebab-case，如 `@update:model-value` 或 `@submit-form`。

## 4. 样式与视图
- **样式隔离**：除非是全局通用样式，否则组件内的样式必须带有 `<style scoped>`，防止样式污染。
- **避免硬编码**：界面上的提示文本、默认配置项等，优先提取为组件顶部的常量或单独的配置对象。