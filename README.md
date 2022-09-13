<?php
$numeros = [53, 82, 80, 66, 41, 64, 28, 99, 77, 57];

echo "Soma: " . array_sum($numeros);

echo "Maior: " . max($numeros);
echo "Menor: " . min($numeros);
echo "Média: " . (array_sum($numeros)) / count($numeros);
?>

<?php
$numbers = [53, 82, 80, 66, 41, 64, 28, 99, 77, 50];

echo "<br><br> (EX2) O valor máximo é: " .max($numbers) ;
echo "<br> (EX2) O valor minimo é: ". min($numbers);
echo "<br> (EX2) o valor médio é: " .array_sum($numbers)/ count($numbers);
?>

