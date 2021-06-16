# Tableau-et-trie
Remplir un tableau, le trier par ordre décroissant et l'utliser

//// Init le tableau
$tab = [];
//// Remplie le tableau $tab pour utiliser plus facilement les données
			foreach($array1 as $child) {
      $tab[] = [
					    'annee' => intval($anneeFichier),
                        'intitule' => $intitule,
                        'chemin' => $chemin,
                        'nomFichier' => $nomFichier
                    ];
    	}
      //// Effectue le trie si respect de la condition
         if ($tri === 'recent') {
         //// Définir un index avec le array_column()
              $annees = array_column($tab, 'annee');
         //// Trier le tableau en utilisant l'index précédent et en lui indiquant l'ordre de tri en 2ième paramètres
              array_multisort($annees, SORT_DESC, $tab);
          }
          //// Utiliser le tableau du'il soit trier ou non
          foreach ($tab as $row){
              $retour .='<tr><td>'.$row['intitule'].'</td><td style="text-align:right;"><a href="download/openPDF.php?chemin='.$row['chemin'].'&fichier='.$row['nomFichier'][3][0].'" target="_blank" class="btn btn-info btn-mini goPDF"><i class="fa fa-file-pdf-o"></i></a></tr></td>';
          }
