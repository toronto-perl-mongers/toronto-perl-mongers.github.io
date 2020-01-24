<ul>
  {{ range .Params.talks }}
  <li>
    <div>
    {{ $talk_url := path.Join "/talks" (. | urlize) }}
    {{ $talk := $.Site.GetPage $talk_url }}
    <a href="{{ $talk_url }}">{{ $talk.Params.title }}</a> ::
    {{ range $talk.Params.presenters }}
      {{ $presenter_url := printf "/presenters/%s" (. | urlize) }}
      {{ $presenter := $.Site.GetPage $presenter_url }}
      <a href="{{ $presenter_url }}">{{ $presenter.Params.name }}</a>
    {{ end }}
    </div>
    <div>
    {{ with $talk.Params.summary }}
      {{ . }}
    {{ else }}
      {{ $talk.Content }}
    {{ end }}
    </div>
  </li>
  {{ end }}
</ul>