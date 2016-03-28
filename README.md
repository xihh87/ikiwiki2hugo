This script helps you migrate individual posts from
[ikiwiki](https://ikiwiki.info/ "One of the first wikis using git as backend.")
to [HUGO](http://gohugo.io/ "A static content generator.").

You could call this script like:

```
$ for post in *.mdwn; do
    ikiwiki2markdown $post > $post.2
    mv $post.2 $post
done
```

Then you should rename it to .md in order for HUGO to see them.

```
$ for post in *.mdwn; do
    git mv $post ${post%%.mdwn}.md
done
```

That should take care of most of the content migration.

This is your content folder now.
