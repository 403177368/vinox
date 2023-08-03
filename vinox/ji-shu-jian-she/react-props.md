# React Props

Pass ReactElement as prop

Pass component as prop

Pass function as prop / Render Prop



What is the difference?

```tsx
function Header({ title }: { title: string }) {
  return <h1>{ title }</h1>;
}

// Pass ReactElement as prop
function Parent() {
  const [title] = useState(() => 'Hello world');

  return (
    <div>
      <Layout header={<Header title={title} />} />
    </div>
  );
}
```
