# Fjärde steget: Lägg till en knapp som slumpar fram en pokemon

Detta steget kommer du få mindre hjälp och få leta fram lösningen själv!

Du har redan lagt till en HTML-knapp tidigare. Så gör bara samma sak igen och lägg till en ny knapp som man skall klicka på för att slumpa.

Eftersom pokeApi-servern antingen kan ta ett namn **eller en siffra**, så kan vi istället för att klistra på texten från vårat textfält på adressen, klistra på en slumpmässig siffra!

```
angular
  .module('pokeDexApp', []) //Skapa angular-appen
  .controller('pokeCtrl', pokeCtrl); //Skapa en controller

function pokeCtrl($scope, $http){
  var serverUrl = 'http://pokeapi.co/api/v2/pokemon/';
  $scope.name = "pikachu";
  
  $scope.getPokemon = function(){
    $http.get(serverUrl + $scope.name).then(showPokemon);
  }
  
  $scope.getRandomPokemon = function(){
    // Modifiera denna raden så att du hämtar en slumpmässig pokemon
    $http.get(serverUrl + $scope.name).then(showPokemon);
  }
  
  function showPokemon(pokemon){
    $scope.pokemon = pokemon.data;
  }
}
```

Lycka till! :)

###[Gå till steg 5](https://github.com/amygdaloideum/SBAB-pokedex-helloworld/tree/master/docs/phase-5)