{{ if eq .Section "meetings" | and (isset .Params "meetingdate") }}
  {{ dateFormat $.Site.Params.navMeetingDate .Params.meetingdate }}
{{ else }}
{{ .Title | markdownify }}
{{ end }}
