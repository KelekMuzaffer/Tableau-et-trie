# Tableau-et-trie
<br/> Remplir un tableau, le trier par ordre décroissant et l'utliser

<br/> //// Init le tableau
<br/> $tab = [];
<br/> //// Remplie le tableau $tab pour utiliser plus facilement les données
<br/> 			foreach($array1 as $child) {
<br/>       $tab[] = [
<br/> 					    'annee' => intval($anneeFichier),
<br/>                         'intitule' => $intitule,
<br/>                         'chemin' => $chemin,
<br/>                         'nomFichier' => $nomFichier
<br/>                     ];
<br/>     	}
<br/>      //// Effectue le trie si respect de la condition
<br/>          if ($tri === 'recent') {
<br/>          //// Définir un index avec le array_column()
<br/>               $annees = array_column($tab, 'annee');
<br/>          //// Trier le tableau en utilisant l'index précédent et en lui indiquant l'ordre de tri en 2ième paramètres
<br/>               array_multisort($annees, SORT_DESC, $tab);
<br/>           }
<br/>           //// Utiliser le tableau du'il soit trier ou non
<br/>           foreach ($tab as $row){
<br/>               $retour .='<tr><td>'.$row['intitule'].'</td><td style="text-align:right;"><a href="download/openPDF.php?chemin='.$row['chemin'].'&fichier='.$row['nomFichier'][3] <br/>   [0].'" target="_blank" class="btn btn-info btn-mini goPDF"><i class="fa fa-file-pdf-o"></i></a></tr></td>';
<br/>           }
