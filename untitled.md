# Untitled

## À propos des mises à jour de version de Dependabot 

Dependabot simplifie la maintenance de vos dépendances. Vous pouvez l'utiliser pour vous assurer que votre référentiel est automatiquement mis à jour avec les dernières versions des packages et des applications dont il dépend.

Vous activez les mises à jour de version de Dependabot en archivant un fichier de configuration dans votre référentiel. Le fichier de configuration spécifie l'emplacement du manifeste, ou d'autres fichiers de définition de package, stockés dans votre référentiel. Dependabot utilise ces informations pour rechercher des packages et des applications obsolètes. Dependabot détermine s'il existe une nouvelle version d'une dépendance en examinant le versionnage sémantique \(semver\) de la dépendance pour décider si elle doit se mettre à jour vers cette version. Pour certains gestionnaires de packages, les mises à jour de version de Dependabot prennent également en charge la commercialisation. Les dépendances vendues \(ou mises en cache\) sont des dépendances qui sont archivées dans un répertoire spécifique dans un référentiel plutôt que référencées dans un manifeste. Les dépendances vendues sont disponibles au moment de la construction même si les serveurs de packages ne sont pas disponibles. Les mises à jour de version de Dependabot peuvent être configurées pour vérifier les dépendances vendues pour les nouvelles versions et les mettre à jour si nécessaire.

Lorsque Dependabot identifie une dépendance obsolète, il déclenche une demande d'extraction pour mettre à jour le manifeste vers la dernière version de la dépendance. Pour les dépendances vendues, Dependabot déclenche une pull request pour remplacer directement la dépendance obsolète par la nouvelle version. Vous vérifiez que vos tests réussissent, examinez le journal des modifications et les notes de publication inclus dans le résumé de la demande d'extraction, puis fusionnez-le. Pour plus d'informations, consultez «Activation et désactivation des mises à jour de version».

Si vous activez les mises à jour de sécurité, Dependabot génère également des pull requests pour mettre à jour les dépendances vulnérables. Pour plus d'informations, consultez «À propos des mises à jour de sécurité de Dependabot».

Dependabot et toutes les fonctionnalités associées sont couverts par les conditions d'utilisation de GitHub.

## Fréquence des demandes d'extraction Dependabot 

Vous spécifiez la fréquence de vérification de chaque écosystème pour les nouvelles versions dans le fichier de configuration: quotidienne, hebdomadaire ou mensuelle.

Lorsque vous activez les mises à jour de version pour la première fois, vous pouvez avoir de nombreuses dépendances qui sont obsolètes et certaines peuvent être plusieurs versions derrière la dernière version. Dependabot vérifie les dépendances obsolètes dès qu'il est activé. Vous pouvez voir de nouvelles demandes d'extraction pour les mises à jour de version quelques minutes après l'ajout du fichier de configuration, en fonction du nombre de fichiers manifest pour lesquels vous configurez les mises à jour.

Pour que les demandes d'extraction restent gérables et faciles à examiner, Dependabot génère un maximum de cinq demandes d'extraction pour commencer à mettre les dépendances à la dernière version. Si vous fusionnez certaines de ces premières demandes d'extraction avant la prochaine mise à jour planifiée, d'autres demandes d'extraction sont ouvertes jusqu'à un maximum de cinq \(vous pouvez modifier cette limite\).

Si vous avez activé les mises à jour de sécurité, vous verrez parfois des demandes d'extraction supplémentaires pour les mises à jour de sécurité. Celles-ci sont déclenchées par une alerte Dependabot pour une dépendance sur votre branche par défaut. Dependabot déclenche automatiquement une pull request pour mettre à jour la dépendance vulnérable.

## Dépôts et écosystèmes pris en charge

Vous pouvez configurer les mises à jour de version pour les référentiels qui contiennent un manifeste de dépendance ou un fichier de verrouillage pour l'un des gestionnaires de packages pris en charge. Pour certains gestionnaires de packages, vous pouvez également configurer la commercialisation des dépendances. Pour plus d'informations, consultez «Options de configuration pour les mises à jour des dépendances».

## Activation et désactivation des mises à jour de version

......

Vous pouvez configurer votre référentiel afin que Dependabot mette à jour automatiquement les packages que vous utilisez.

Les personnes disposant d'autorisations d'écriture sur un référentiel peuvent activer ou désactiver les mises à jour de version de Dependabot pour le référentiel.

## À propos des mises à jour de version pour les dépendances 

Vous activez les mises à jour de version de Dependabot en archivant un fichier de configuration dependabot.yml dans le répertoire .github de votre référentiel. Dependabot génère ensuite des pull requests pour maintenir à jour les dépendances que vous configurez. Pour les dépendances de chaque gestionnaire de packages que vous souhaitez mettre à jour, vous devez spécifier l'emplacement des fichiers manifestes du package et la fréquence à laquelle vérifier les mises à jour des dépendances répertoriées dans ces fichiers. Pour plus d'informations sur l'activation des mises à jour de sécurité, consultez «Configuration des mises à jour de sécurité Dependabot».

Lorsque vous activez les mises à jour de version pour la première fois, vous pouvez avoir de nombreuses dépendances qui sont obsolètes et certaines peuvent être plusieurs versions derrière la dernière version. Dependabot vérifie les dépendances obsolètes dès qu'il est activé. Vous pouvez voir de nouvelles demandes d'extraction pour les mises à jour de version quelques minutes après l'ajout du fichier de configuration, en fonction du nombre de fichiers manifest pour lesquels vous configurez les mises à jour.

Pour que les demandes d'extraction restent gérables et faciles à examiner, Dependabot génère un maximum de cinq demandes d'extraction pour commencer à mettre les dépendances à la dernière version. Si vous fusionnez certaines de ces premières demandes d'extraction avant la prochaine mise à jour planifiée, d'autres demandes d'extraction sont ouvertes jusqu'à un maximum de cinq \(vous pouvez modifier cette limite\). Pour plus d'informations, voir «Personnalisation des mises à jour des dépendances».

Lors de l'exécution de mises à jour de sécurité ou de version, certains écosystèmes doivent être en mesure de résoudre toutes les dépendances à partir de leur source pour vérifier que les mises à jour ont réussi. Si vos fichiers manifestes ou verrouillés contiennent des dépendances privées, Dependabot doit pouvoir accéder à l'emplacement où ces dépendances sont hébergées. Les propriétaires d'organisation peuvent accorder à Dependabot l'accès aux référentiels privés contenant des dépendances pour un projet au sein de la même organisation. Pour plus d'informations, voir «Gestion des paramètres de sécurité et d'analyse pour votre organisation».

Actuellement, les mises à jour de version de Dependabot ne prennent pas en charge les fichiers manifestes ou verrouillés contenant des dépendances hébergées dans des registres privés ou dans des référentiels GitHub privés appartenant à une organisation différente de celle du projet dépendant. De plus, Dependabot ne prend pas en charge les dépendances GitHub privées pour tous les gestionnaires de packages. Pour plus d'informations, consultez «À propos des mises à jour de version de Dependabot».

## Activation des mises à jour de version de Dependabot

1. Créez un fichier de configuration dependabot.yml. 
2. Utilisez package-écosystème pour spécifier les gestionnaires de packages à surveiller. 
3. Pour chaque gestionnaire de packages, utilisez: 
   1. répertoire pour spécifier l'emplacement du manifeste ou d'autres fichiers de définition. 
   2. schedule.interval pour spécifier la fréquence de vérification des nouvelles versions. 
4. Archivez le fichier de configuration dependabot.yml dans le répertoire .github du référentiel. 

Exemple de fichier dependabot.yml 

L'exemple de fichier dependabot.yml ci-dessous configure les mises à jour de version pour deux gestionnaires de packages: npm et Docker. Lorsque ce fichier est archivé, Dependabot vérifie les fichiers manifestes sur la branche par défaut pour les dépendances obsolètes. S'il trouve des dépendances obsolètes, il lèvera des requêtes d'extraction sur la branche par défaut pour mettre à jour les dépendances.

## Activation des mises à jour de version sur les fourches 

Si vous souhaitez activer les mises à jour de version sur les fourches, il y a une étape supplémentaire. Les mises à jour de version ne sont pas automatiquement activées sur les fourches lorsqu'un fichier de configuration dependabot.yml est présent. Cela garantit que les propriétaires de fourches n'activent pas involontairement les mises à jour de version lorsqu'ils extraient des modifications, y compris un fichier de configuration dependabot.yml du référentiel d'origine.

Sur un fork, vous devez également activer explicitement Dependabot.

1. Sur GitHub, accédez à la page principale du référentiel. 
2. Sous le nom de votre référentiel, cliquez sur Insights. 
3. Dans la barre latérale gauche, cliquez sur Graphique de dépendance. 
4. Sous "Graphique de dépendance", cliquez sur Dependabot. 
5. Sous «Activer Dependabot», cliquez sur Activer Dependabot.

## Vérification de l'état des mises à jour de version 

Après avoir activé les mises à jour de version, vous verrez un nouvel onglet Dependabot dans le graphique de dépendances pour le référentiel. Cet onglet montre quels gestionnaires de packages Dependabot est configuré pour surveiller et quand Dependabot a vérifié pour la dernière fois les nouvelles versions.

## Désactivation des mises à jour de version de Dependabot 

Vous pouvez désactiver entièrement les mises à jour de version en supprimant le fichier dependabot.yml de votre référentiel. Plus généralement, vous souhaitez désactiver temporairement les mises à jour pour une ou plusieurs dépendances ou gestionnaires de packages.

* Gestionnaires de packages: désactivez en définissant open-pull-requests-limit: 0 ou en commentant l'écosystème de packages pertinent dans le fichier de configuration.
* Dépendances spécifiques: désactivez en ajoutant des attributs ignorés pour les packages ou les applications que vous souhaitez exclure des mises à jour. 

Lorsque vous désactivez les dépendances, vous pouvez utiliser des caractères génériques pour faire correspondre un ensemble de bibliothèques associées. Vous pouvez également spécifier les versions à exclure. Ceci est particulièrement utile si vous devez bloquer les mises à jour d'une bibliothèque, en attente de travail pour prendre en charge une modification de rupture de son API, mais que vous souhaitez obtenir des correctifs de sécurité pour la version que vous utilisez.

Exemple de désactivation des mises à jour de version pour certaines dépendances 

L'exemple de fichier dependabot.yml ci-dessous comprend des exemples des différentes façons de désactiver les mises à jour de certaines dépendances, tout en permettant à d'autres mises à jour de continuer.

## Liste des dépendances configurées pour les mises à jour de version 

Vous pouvez afficher les dépendances que Dependabot surveille pour les mises à jour.

## Affichage des dépendances surveillées par Dependabot

Après avoir activé les mises à jour de version, vous pouvez confirmer que votre configuration est correcte à l'aide de l'onglet Dependabot dans le graphique de dépendances pour le référentiel. Pour plus d'informations, consultez «Activation et désactivation des mises à jour de version».

1. Sur GitHub, accédez à la page principale du référentiel. 
2. Sous le nom de votre référentiel, cliquez sur Insights. 
3. Dans la barre latérale gauche, cliquez sur Graphique de dépendance. 
4. Sous "Graphique de dépendance", cliquez sur Dependabot. 
5. Si vous le souhaitez, pour afficher les fichiers contrôlés pour un gestionnaire de packages, cliquez sur le fichier associé. 

Si des dépendances sont manquantes, recherchez des erreurs dans les fichiers journaux. 

Si des gestionnaires de packages sont manquants, consultez le fichier de configuration.

## Affichage des fichiers journaux Dependabot

1. Dans l'onglet Dependabot, cliquez sur Dernière vérification il y a TIME pour afficher le fichier journal généré par Dependabot lors de la dernière vérification des mises à jour de version. 
2. Si vous le souhaitez, pour réexécuter la vérification de version, cliquez sur Rechercher les mises à jour.

## Options de configuration pour les mises à jour des dépendances

....



