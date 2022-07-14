<script>
export default {
  name: 'UserAvatarFunctional',

  functional: true,

  render(h, context) {
    // <figure class="avatar">
    //   <img :src="props.user.avatar" :alt="props.user.name">
    //   <button @click.stop="listeners.contact">Contact me</button>
    // </figure>

    return h('div', { class: 'avatar' },
      [h('figure',
        [h('img', { attrs: { src: context.props.avatar, alt: 'Jane Doe' } })])
      ]
    )
  }
}
</script>
