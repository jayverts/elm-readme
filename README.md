# elm-readme
-----------

#about elm
--------
Elm was initially designed by Evan Czaplicki as his thesis in 2012. - wiki

Elm programs render HTML through a virtual DOM, and may interoperate with other code by using "JavaScript as a service". -wiki

Elm has a module system that allows users to break their code into smaller parts called modules. Modules can hide implementation details such as helper functions, and group related code together -wiki

The logic of every Elm program will break up into three cleanly separated parts:

Model — the state of your application
Update — a way to update your state
View — a way to view your state as HTML 
- elm-lang.org

Notice that function application looks different than in languages like JavaScript and Python and Java. Instead of wrapping all arguments in parentheses and separating them with commas, we use spaces to apply the function. So (add(3,4)) becomes (add 3 4) which ends up avoiding a bunch of parens and commas as things get bigger. Ultimately, this looks much cleaner once you get used to it! The elm-html package is a good example of how this keeps things feeling light.
-elm-lang.org




# sample problem
-----------

import Html exposing (beginnerProgram, div, button, text)
import Html.Events exposing (onClick)


main =
  beginnerProgram { model = 0, view = view, update = update }


view model =
  div []
    [ button [ onClick Decrement ] [ text "-" ]
    , div [] [ text (toString model) ]
    , button [ onClick Increment ] [ text "+" ]
    ]


type Msg = Increment | Decrement


update msg model =
  case msg of
    Increment ->
      model + 1

    Decrement ->
      model - 1
