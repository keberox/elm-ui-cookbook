# elm-ui-cookbook

## Centralize Input.text contents

mthiems 2:33 AM
@VPagani I've seen this before, and I think this may be a bug in the current version of elm-ui. It seems the `input` DOM element needs a `text-align: inherit` style, as the `text-align: center` is on a parent `div` instead of on the `input` itself. Here's an Ellie illustrating one option for a workaround that makes it work:
https://ellie-app.com/6GQLrcSt7hWa1

mgriffith:bulb: 3:06 AM
Ah, yeah, the current way to do that is to capture your spacing a font values in a palette file and always use those.  Then you could do things like set the padding based on font size or whatever you’d like.

https://elmlang.slack.com #elm-ui

## Structuring code

blackeuler 4:46 AM
Is there any strategy when it comes to structing the code? I feel like I have a lot of code in the one file all mainly for the view of the page.

mgriffithbulb 4:58 AM
First suggestion is to take all values and put them in one file (colors, spacing/padding values, font sizes and font families). I usually call this file UI After that, if you find a reusable part of a view, I’d put it in it’s own sub module. So, buttons go in UI.Button. Though it’s also fine to have big files.

https://elmlang.slack.com #elm-ui

## Break long text without spaces

```
row [ width fill ]
  [ paragraph
    [ Font.color model.style.color
    , Font.size 40
	, Html.Attributes.style "word-break" "break-all" |> htmlAttribute
    ]
    [ text model.status.filename ]
  ]
```

- https://stackoverflow.com/questions/36150458/flex-item-overflows-container-due-to-long-word-even-after-using-word-wrap/36150638#36150638

`'overflow-wrap: break-word'` will not work when `paragraph` inside `row` so this solution https://stackoverflow.com/questions/3058866/how-to-force-a-line-break-in-a-long-word-in-a-div/3059128#3059128 is bad for flexbox.

## Center wrapped flexbox

You can't

https://stackoverflow.com/questions/32802202/how-to-center-a-flex-container-but-left-align-flex-items/32811002#32811002

## Custom events

Examples in source code https://github.com/mdgriffith/elm-ui/blob/1.1.5/src/Element/Events.elm#L177 but are not exported

## Mouse click coordinates

Examples in source code but on exported https://github.com/mdgriffith/elm-ui/blob/1.1.5/src/Element/Events.elm#L115
