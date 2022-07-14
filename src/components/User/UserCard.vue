<script>
  export default {
    name: 'UserCard',

    functional: true,

    render(h, context) {
      const figureBlock = h('figure', {
        class: 'avatar'
      }, [
        h('img', {
          attrs: {
            src: context.props.user.avatar,
            alt: context.props.user.name
          }
        }),
        h(
          'button',
          {
            on: {
              click(e) {
                e.stopPropagation()
                context.listeners.contact()
              }
            }
          },
          'Contact me'
        )
      ])
      const additionalBlocak = h('div', {
        class: 'additional' }, [figureBlock])

      const moreInfoBlock = h('div', {
        class: 'more-info' }, [
          h('h1', context.props.user.name),
          h('h3', context.props.user.role),
          h('p', context.children)
        ])

      return h('div', {class: 'card',
          on: context.listeners
        },
        [
          additionalBlocak,
          moreInfoBlock
        ]
      )
    }
  }
</script>