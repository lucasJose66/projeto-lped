
<script>
    let puzzle = [
      [1, 2, 3],
      [4, 5, 6],
      [7, 8, 9]
    ];
  
    let selectedPiece = null;
  
    function printPuzzle() {
      puzzle.forEach(row => {
        let rowString = "";
        row.forEach(cell => {
          rowString += (cell === null ? " " : cell) + " ";
        });
        console.log(rowString);
      });
    }
  
    function shufflePuzzle() {
      const flattenedPuzzle = puzzle.flat();
      for (let i = flattenedPuzzle.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [flattenedPuzzle[i], flattenedPuzzle[j]] = [flattenedPuzzle[j], flattenedPuzzle[i]];
      }
      puzzle = [
        flattenedPuzzle.slice(0, 3),
        flattenedPuzzle.slice(3, 6),
        flattenedPuzzle.slice(6, 9)
      ];
      printPuzzle();
    }
  
    function checkCompletion() {
  const flattenedPuzzle = puzzle.flat();
  const correctOrder = [1, 2, 3, 4, 5, 6, 7, 8, 9];
  
  if (JSON.stringify(flattenedPuzzle) === JSON.stringify(correctOrder)) {
    console.log("Quebra-cabeça completo!");
    // Exibir mensagem de conclusão aqui
  }
}

  
    function movePiece(row, col) {
      if (row < 0 || row >= puzzle.length || col < 0 || col >= puzzle[row].length) {
        console.log("Posição inválida!");
        return;
      }
  
      if (puzzle[row][col] === null) {
        console.log("Posição vazia!");
        return;
      }
  
      if (selectedPiece === null) {
        selectedPiece = { row, col };
        console.log("Peça selecionada: ", puzzle[row][col]);
      } else {
        const { row: prevRow, col: prevCol } = selectedPiece;
  
        // Realiza a troca de posições
        const temp = puzzle[prevRow][prevCol];
        puzzle[prevRow][prevCol] = puzzle[row][col];
        puzzle[row][col] = temp;
  
        // Limpa a seleção
        selectedPiece = null;
  
        console.log("Movimento realizado!");
        printPuzzle();
        checkCompletion();
      }
    }
  
    function handleClick(row, col) {
      movePiece(row, col);
    }
  
    // Embaralhar o quebra-cabeça ao carregar a página
    shufflePuzzle();
  </script>
  
  <style>
    .puzzle-container {
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }
  
    .puzzle {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      grid-gap: 10px;
      width: 250px;
    }
  
    .puzzle-cell {
      width: 80px;
      height: 80px;
      border: 1px solid #000;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
    }
    
  </style>
  
  <div class="puzzle-container">
    <div class="puzzle">
      {#each puzzle as row, i}
        {#each row as cell, j}
          <div class="puzzle-cell" on:click={() => handleClick(i, j)}>
            {#if cell !== null}
              <img src={`imagens/${cell}1.jpg`} alt={`Peça ${cell}`} />
            {/if}
          </div>
        {/each}
      {/each}
    </div>
  </div>
  