## Suspense with a custom hook

the difference between useEffect and useLayoutEffect is when they run.

browser paints when all your javascript is run

useLayoutEffect runs before the paint, useEffect will run after the paint.

Most code that you write doesn't need to be ran before paint - we are using useLayoutEffect because useEffect has a exhaustive deps bug in it with useTransition inside it.
