# Temporary Fix for [ANW-269](https://archivesspace.atlassian.net/browse/ANW-269)

## Summary

This plugin provides temporary implementation of the fix provided in
[ArchivesSpace Pull Request #1447](https://github.com/archivesspace/archivesspace/pull/1447) until it
or a similar fix is available in a release.

## Description
Updates PDF template to use the raw record display string, rather than the (now default) HTML escaped form, so that the tags are 1) not visible and 2) available for CSS styling.

## Related JIRA Ticket or GitHub Issue
[ANW-269](https://archivesspace.atlassian.net/browse/ANW-269) HTML tags are inappropriately generated from the HTML to PDF process for the PUI, but only at the Collection Inventory level.

## Motivation and Context
Fixes problem described in ANW-269. Tags in "Collection Inventory" record display strings were displayed as such, rather than being rendered into the appropriate style by the PDF CSS.

For example, the string: 
`<span class="italic title">Zeniada</span> Notes, 1981`
rendered as
`<span class="italic title">Zeniada</span> Notes, 1981`
rather than
_Zeniada_ Notes, 1981

---

## Activate the plugin
- Install the plugin:
  - Clone this repository into the plugins/pdf_public_anw_269; or
  - Unzip the release zip into the plugins/pdf_public_anw_269.

- Enable the plugin:
  - In config/config.rb, append the plugin name to the "AppConfig[:plugins]" list, e.g.:

    AppConfig[:plugins] << ['pdf_public_anw_269']
    
    or
    
    AppConfig[:plugins] = [...existing plugins..., 'pdf_public_anw_269']

- Restart ArchivesSpace
