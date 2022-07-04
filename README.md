# assignment-1

1-1
// -----------Task 1-1 with Elm-------------\\
```
module Main exposing (main)

import Browser
import Html exposing (Html, button, div, text)
import Html.Events exposing (onClick)


type alias Model =
    { baseUrl : String }


initialModel : Model
initialModel =
    { baseUrl = "https://localhost:5000/" }


type Msg
    = 
    BuildUrl

addStrings a b c = a++b++c
buildUrl d a b = d a b "vehicles/"
update : Msg -> Model -> Model
update msg model =
    case msg of
        BuildUrl ->
            { model | baseUrl = model.baseUrl ++ buildUrl addStrings "Toyota/" "Corolla-Cross/" }


view : Model -> Html Msg
view model =
    div []
        [button [ onClick BuildUrl ] [ text "Search a Car" ]
        , div [] [ text <| model.baseUrl ]
        ]
        


main : Program () Model Msg
main =
    Browser.sandbox
        { init = initialModel
        , view = view
        , update = update
 
 ```}
//----------------1-2 with ts-----------------\\
```
```
function add(a: number, b: number) {
 return a + b;
}

function curryFunc(c: number)  {
 return function (a: number) {
     return function (b: number) {
         return a + b;
     };
 };
}
add(1, 2);
console.log(curryFunc(3));
```
//----------------------2-1---------------------------\\
// pipeline definition
```
const isTextLongEnough: (text: string) => boolean =
  text => isGreaterThan5(increasedNum(getNumberOfCharacters(text)))

console.log(isTextLongEnough('abc')) // false
console.log(isTextLongEnough('abcde')) // true

const getNumberOfCharacters = (text: string): number => {
  return text.length;
};
const increasedNum = (getNumberOfCharacters: number): number => {
  return getNumberOfCharacters + 1;
};
const isGreaterThan5 = (increasedNum: number): boolean => {
  if (increasedNum > 2) {
    return true;
  }
  return false;
};
```
```
//--------------------------2-2-------------------------------\\

```
```
const evenNumbers = [1, 2, 3, 4].filter(n => n % 2 === 0)
// or the shorter version: [1, 2, 3, 4].filter(isEven)
const enum Shape {
    BlueSquare,
    GreenCircle,
    RedDiamond
  }
  
  function createShapes(
    volume: number,
    generateShape: () => Shape
  ): Shape[] {
    return [...new Array(volume)].map(() => generateShape())
  }
```
```
//------------------------------------------------- 3------------------------------------------------------\\
type UnaryFunction<A, B> = (_: A) => B;
type BinaryFunction<A, B, C> = (_1: A, _2: B) => C;

const partialApplication = <A, B, C>(
  g: BinaryFunction<A, B, C>,
  a: A
): UnaryFunction<B, C> => {return(b:B): C => {
        return g(a,b)
}};
```
