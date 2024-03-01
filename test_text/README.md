# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Как все работает
Для начала имеются 4 компонента где в каждом находится одно четверостишье с целью более удобного взаимодействия с каждым четверостишьем отдельно.

вся логика находится в файле main_text.vue (src/components/main_text.vue)
первая функция это эффект нажатия кнопки происходит путем добавления класса к стилям кнопки путем изменения булевой переменной и внесения в ее аргументы индекса элемента  this.isActive[buttonNumber] = !this.isActive[buttonNumber];
и таким же образом происходит отображение компонентов только при помощи директивы v-if для избежания изменения стилей.

Затем идет функция которая берет объект isActive с булевыми данными и фильтрует их по количеству истинных значений и возвращает длинну объекта. Если количество активных компонентов меньше 3 или если компонент, который собираются переключить, в  активен, то функция переключает видимость компонента. в ином случае убрать компонент нельзя.

