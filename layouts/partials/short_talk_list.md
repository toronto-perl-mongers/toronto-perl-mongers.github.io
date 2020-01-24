<ul>
  {{ range $t := .Params.talks }}
  <li>
    {{ $talk_url := path.Join "/talks" ($t | urlize) }}
    {{ $talk := $.Site.GetPage $talk_url }}
    <a href="{{ $talk_url }}">{{ $talk.Params.title }}</a> ::
    {{ range $talk.Params.presenters }}
      {{ $presenter_url := printf "/presenters/%s" (. | urlize) }}
      {{ $presenter := $.Site.GetPage $presenter_url }}
      <a href="{{ $presenter_url }}">{{ $presenter.Params.name }}</a>
    {{ end }}
  </li>
  {{ end }}
</ul>
