# Link DB API
The Link DB API is used to interract with linkdb outside of the official frontend and is also used in said frontend.
It is a REST API that may be self hosted for testing purposes or for seperate projects.
There is currently no "canon" linkdb api but we are working on one.

## V1
All routes in this section are prefixed wih `/v1/`

### Posts
`GET`: `/posts?sort=top|bottom&by=likes|age&section=n&section_size=n`

- `sort`: `top` means most-liked or newest posts while `bottom` means least-liked or oldest. Defaults to `top`.
- `by`: sort by likes or age. Defaults to `likes`.
- `section` and `section_size`: return `section_size` posts starting with `section` times `section_size`. Defaults to `1` and `50`.

Schema:
```JSON
{
  "amount": 4, // tends to equal section_size but may be less if there are not enough posts or may be zero if there are no posts in the section.	
  "posts": [
    {
	  "title": "Why linkdb rules the world",
	  "describtion": "Read about the linkdb blogging service",
	  "date": "2002-06-01 04-54-3",
	  "link": "https://example.com/blog/osdfjs"
	}
	// `amount` posts will follow
  ]
}
```

### Users
### Sessions