# Sudoku Solver

Application full-stack JavaScript permettant de résoudre une grille de Sudoku et de vérifier si un nombre peut être placé sur une case donnée.

## Auteur

Dieu-Merci Ndenga

## Fonctionnalités

- Résolution de puzzles valides de 81 caractères.
- Validation des caractères et de la longueur d'un puzzle.
- Vérification des conflits de ligne, colonne et région 3 x 3.
- Interface web simple pour résoudre une grille ou vérifier un placement.
- API JSON utilisable indépendamment de l'interface.

## Installation

```bash
npm install
cp sample.env .env
npm start
```

L'application est disponible sur `http://localhost:3000`.

## API

### `POST /api/solve`

Reçoit un objet JSON contenant `puzzle`, une chaîne composée de chiffres de 1 à 9 et de points `.`.

```json
{
	"puzzle": "..9..5.1.85.4....2432......1...69.83.9.....6.62.71...9......1945....4.37.4.3..6.."
}
```

Retourne `{ "solution": "..." }` ou un objet `{ "error": "..." }` décrivant l'erreur.

### `POST /api/check`

Reçoit `puzzle`, `coordinate` et `value`. Une coordonnée utilise une lettre de `A` à `I` suivie d'un chiffre de `1` à `9`, par exemple `A1`.

Retourne `{ "valid": true }` lorsque le placement est possible. En cas de conflit, la réponse contient aussi `conflict` avec les contraintes concernées.

## Tests

```bash
npm test
```

Le projet contient 12 tests unitaires et 14 tests fonctionnels couvrant le solveur et les routes HTTP.

## Licence

MIT
