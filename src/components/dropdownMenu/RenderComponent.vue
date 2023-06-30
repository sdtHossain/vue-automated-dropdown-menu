<script lang="ts">
import { h } from 'vue'
import { RouterLink } from 'vue-router'
const DropdownRender = {
  name: 'Dropdown',
  props: ['menuItem'],
  render(props) {
    return [
      props.menuItem.submenu
        ? h('li', { class: ['dropdown-nav-menu', 'py-1', 'px-3'] }, [
            h(RouterLink, {
              to:
                props.menuItem.id == 1
                  ? { name: 'about' }
                  : { name: 'contact', params: { id: props.menuItem.id } },
              innerHTML: props.menuItem.title
            }),
            h('ul', { class: 'submenu nav-menu list-unstyled' }, [
              props.menuItem.submenu.map((o) => h(DropdownRender, { menuItem: o }))
            ])
          ])
        : h('li', { class: ['dropdown-nav-menu', 'py-1', 'px-3'] }, [
            h(RouterLink, {
              to:
                props.menuItem.id == 1
                  ? { name: 'about' }
                  : { name: 'contact', params: { id: props.menuItem.id } },
              innerHTML: props.menuItem.title
            })
          ])
    ]
  }
}

// h('li', [
//         h(RouterLink, { to: `/${props.content.id}/contact`, innerHTML: props.content.label })
//       ]),

// props.content.children
//   ? h('ul', [
//       props.content.children.map((o) =>
//         h(ListItem, {
//           content: o
//         })
//       )
//     ])
//   : []

export default DropdownRender
</script>
