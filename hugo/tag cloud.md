```
{{ range .Site.Taxonomies.tags }}
	<a href="{{ .Page.Permalink }}">{{ .Page.Title }}</a>&nbsp;
{{ end }}
```
