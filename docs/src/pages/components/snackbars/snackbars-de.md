---
title: Snackbar React-Komponente
components: Snackbar, SnackbarContent
---

# Snackbar

<p class="description">Snackbars provide brief messages about app processes. The component is also known as a toast.</p>

[Snackbars](https://material.io/design/components/snackbars.html) informieren Benutzer über einen Prozess, den eine App ausgeführt hat oder ausführen wird. Sie erscheinen vorübergehend am unteren Rand des Bildschirms. Sie sollten die Benutzererfahrung nicht unterbrechen und erfordern keine Benutzereingaben, um verschwinden zu können.

Snackbars contain a single line of text directly related to the operation performed. They may contain a text action, but no icons. You can use them to display notifications.

#### Häufigkeit

Es kann immer nur eine Snackbar angezeigt werden.

## Einfache Snackbars

Eine einfache Snackbar, die das Verhalten der Snackbar von Google Keep reproduzieren soll.

{{"demo": "pages/components/snackbars/SimpleSnackbar.js"}}

## Benutzerdefinierte Snackbars

Hier sind einige Beispiele, wie man die Komponente anpassen kann. Mehr dazu erfahren Sie auf der [Überschreibungsdokumentationsseite](/customization/components/).

{{"demo": "pages/components/snackbars/CustomizedSnackbars.js"}}

## Positionierte Snackbars

Es kann Situationen geben, in denen die Anordnung der Snackbar flexibler sein muss.

{{"demo": "pages/components/snackbars/PositionedSnackbar.js"}}

## Nachrichtenlänge

Einige Snackbars mit unterschiedlicher Nachrichtenlänge.

{{"demo": "pages/components/snackbars/LongTextSnackbar.js"}}

## Übergänge

### Aufeinanderfolgende Snackbars

Wenn mehrere Snackbar-Aktualisierungen erforderlich sind, sollten diese einzeln und nacheinander angezeigt werden.

{{"demo": "pages/components/snackbars/ConsecutiveSnackbars.js"}}

### Snackbars und schwebende Aktionsschaltflächen (FABs)

Snackbars sollten (auf dem Handy) über FABs angezeigt werden.

{{"demo": "pages/components/snackbars/FabIntegrationSnackbar.js", "iframe": true, "maxWidth": 500}}

### Übergang ändern

[Grow](/components/transitions/#grow) ist der Standardübergang, Sie können jedoch einen anderen verwenden.

{{"demo": "pages/components/snackbars/TransitionsSnackbar.js"}}

### Schieberegler Richtung

Sie können die Richtung des [Gleiten](/components/transitions/#slide) Übergangs ändern.

{{"demo": "pages/components/snackbars/DirectionSnackbar.js"}}

## Ergänzende Projekte

Für fortgeschrittenere Anwendungsfälle können Ihnen folgende Projekte helfen:

### notistack

![stars](https://img.shields.io/github/stars/iamhosseindhv/notistack.svg?style=social&label=Stars) ![npm downloads](https://img.shields.io/npm/dm/notistack.svg)

This example demonstrates how to use [notistack](https://github.com/iamhosseindhv/notistack). notistack has an **imperative API** that makes it easy to display snackbars, without having to handle their open/close state. It also enables you to **stack** them on top of one another (although this is discouraged by the Material Design specification).

{{"demo": "pages/components/snackbars/IntegrationNotistack.js", "defaultCodeOpen": false}}

## Barrierefreiheit

(WAI-ARIA: https://www.w3.org/TR/wai-aria-1.1/#alert)

- Since alerts are not required to receive focus, content authors should not require users to close a Snackbar if the role is set to `alert` through the SnackbarContent `role` prop. This is the default role.
- If a Snackbar requires focus to close it, then content authors should use the `role` of `alertdialog`.

```jsx
<SnackbarContent
  message="This is a Snackbar message."
  role="alert"
/>
```

```jsx
<Snackbar
  ContentProps={{
    'aria-describedby': 'snackbar-fab-message-id',
    'role': 'alertdialog',
  }}
  message={<span id="snackbar-fab-message-id">Archived</span>}
  action={
    <Button color="inherit" size="small">
      Undo
    </Button>
  }
/>
```