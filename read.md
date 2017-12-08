The first argument (child) is any renderable React child, such as an element, string, or fragment. The second argument (container) is a DOM element.

ReactDOM.createPortal(child, container)



Usage
Normally, when you return an element from a component’s render method, it’s mounted into the DOM as a child of the nearest parent node:

render() {
  // React mounts a new div and renders the children into it
  return (
    <div>
      {this.props.children}
    </div>
  );
}


However, sometimes it’s useful to insert a child into a different location in the DOM:

render() {
  // React does *not* create a new div. It renders the children into `domNode`.
  // `domNode` is any valid DOM node, regardless of its location in the DOM.

  return ReactDOM.createPortal(
    this.props.children,
    domNode,
  );
}

A typical use case for portals is when a parent component has an overflow: hidden or z-index style, but you need the child to visually “break out” of its container. For example, dialogs, hovercards, and tooltips.
