<?php
$numeros = [53, 82, 80, 66, 41, 64, 28, 99, 77, 57];

echo "Soma: " . array_sum($numeros);

echo "Maior: " . max($numeros)<br>;
echo "Menor: " . min($numeros)<br>;
echo "Média: " . (array_sum($numeros)) / count($numeros)<br>;
?>

<?php
$numbers = [53, 82, 80, 66, 41, 64, 28, 99, 77, 50];

echo "<br><br> (EX2) O valor máximo é: " .max($numbers) ;
echo "<br> (EX2) O valor minimo é: ". min($numbers);
echo "<br> (EX2) o valor médio é: " .array_sum($numbers)/ count($numbers);
?>



$funcionarios = [
        ['nome' => 'João da Silva', 'genero' => 'M', 'area' => 'engenharia', 'salario' => 6000],
        ['nome' => 'Maria da Silva', 'genero' => 'F', 'area' => 'marketing', 'salario' => 3000],
        ['nome' => 'Beltrano da Silva', 'genero' => 'M', 'area' => 'contabilidade', 'salario' => 4000],
        ['nome' => 'Ciclano Pereira', 'genero' => 'M', 'area' => 'engenharia', 'salario' => 4000],
        ['nome' => 'Fulana Oliveira', 'genero' => 'F', 'area' => 'contabilidade', 'salario' => 2000],
        ['nome' => 'Jão Silveira', 'genero' => 'M', 'area' => 'marketing', 'salario' => 4000],
        ['nome' => 'Cirilo Ferreira', 'genero' => 'M', 'area' => 'contabilidade', 'salario' => 3000],
        ['nome' => 'Zé das Couve', 'genero' => 'M', 'area' => 'engenharia', 'salario' => 5000],
        ['nome' => 'Pedro Pedrada', 'genero' => 'M', 'area' => 'contabilidade', 'salario' => 2000],
        ['nome' => 'Paulo Paulada', 'genero' => 'M', 'area' => 'marketing', 'salario' => 2000],
        ['nome' => 'Creuza Reis', 'genero' => 'F', 'area' => 'financeiro', 'salario' => 1500],
        ['nome' => 'Yarley Ground', 'genero' => 'M', 'area' => 'financeiro', 'salario' => 3000],
        ['nome' => 'Billy Bill', 'genero' => 'M', 'area' => 'marketing', 'salario' => 2000],
        ['nome' => 'Brian Brioche', 'genero' => 'M', 'area' => 'engenharia', 'salario' => 6500],
        ['nome' => 'Mary Mariana', 'genero' => 'F', 'area' => 'financeiro', 'salario' => 2000],
    ];

 
    echo "<br>RESPOSTAS Exercício 3:<br>";

    $maxs=0;
    
    foreach($funcionarios as $funcionario) {
                
        if ($funcionario['salario'] > $maxs) {
            $maxs = $funcionario['salario'];            
        }
    }
   
    echo "<br>O maior salário é  de R$ ". number_format($maxs, 2, ',');

    $somaeng=0;
    $eng=0;
    $somamkt=0;
    $mkt=0;
    $somacont=0;
    $cont=0;
    $somafin=0;
    $fin=0;


    foreach($funcionarios as $funcionario) {

        switch($funcionario['area']) {
            case 'engenharia':
                $somaeng += $funcionario['salario'];
                $eng++;
                break;
            case 'marketing':
                $somamkt += $funcionario['salario'];
                $mkt++;
                break;
            case 'contabilidade':
                $somacont += $funcionario['salario'];
                $cont++;
                break;
            case 'financeiro':
                $somafin += $funcionario['salario'];
                $fin++;
                break;        
        }
    }

    echo "<br><br> Média da Engenharia: R$ ". number_format(($somaeng / $eng), 2, ',');
    echo "<br> Média do Marketing: R$ ". number_format(($somamkt / $mkt), 2, ',');
    echo "<br> Média da Contabilidade: R$ ". number_format(($somacont / $cont), 2, ',');
    echo "<br> Média do Financeiro: R$ ". number_format(($somafin / $fin), 2, ',');

    $feng=0;
    $fmkt=0;
    $fcont=0;
    $ffin=0;

    foreach($funcionarios as $funcionario) {

        switch($funcionario['area']) {
            case 'engenharia':
                if($funcionario['genero'] == 'F') {
                    $feng++;
                }                
                break;
            case 'marketing':
                if($funcionario['genero'] == 'F') {
                    $fmkt++;
                }                
                break;
            case 'contabilidade':
                if($funcionario['genero'] == 'F') {
                    $fcont++;
                }                
                break;
            case 'financeiro':
                if($funcionario['genero'] == 'F') {
                    $ffin++;
                }                
                break;    
        }        
    }

    $femarea = ['engenharia' => $feng, 'marketing' => $fmkt, 'contabilidade' => $fcont, 'financeiro' => $ffin];

    asort($femarea);

    $areamaiorfem = array_key_last($femarea);
    $areamenorfem = array_key_first($femarea);
    $maiorfem = array_pop($femarea);
    $menorfem = array_shift($femarea);

    echo "<br><br> A área que tem mais mulheres é $areamaiorfem com $maiorfem.";
    echo "<br> A área que tem menos mulheres é $areamenorfem com $menorfem.";

    $somasalmasc=0;
    $somasalfem=0;

    foreach($funcionarios as $funcionario) {

        switch($funcionario['genero']) {
            case 'M':
                $somasalmasc += $funcionario['salario'];
                break;
            case 'F':
                $somasalfem += $funcionario['salario'];
                break;
        }
    }

    $salgen = ['Homem' => $somasalmasc, 'Mulher' => $somasalfem];

    asort($salgen);

    $maiorsalgen = array_key_last($salgen);
    $somavalgen = array_pop($salgen);

    echo "<br><br> Gênero que ganha mais é $maiorsalgen com R$ ". number_format(($somavalgen), 2, ',');


