# 2017


## 2017.03.22 - HD - 20.00 (Paris time)

## 2017.03.15 - HD - 20.00 (Paris time)

### Methodology
* @aurelie : feedback on the evolution of the methodology implementation
starter kit
	* github cards
	* gitbooks : on starter kit, and a unique medico-technical gitbook, assembling software and hardware part  
* long discussion on repo structures 
	* each project has its repo + a production repo 
	* or : one giant common repo 
	* pros for separate repos 
		* easy to download
		* “separation of concerns”, maintain a separate environment for development, contribution and enforces an “emulator way of thinking”
		* ease of continuous integration if using “travis”
	* pros for a single repo
		* easy for the user
		* maintain transversality between the repos
		
### Envelope detection challenge
* @soobash: presentation of an other detection envelope algorithm
* @hackolite: learboard should be online tomorrow !!
	* dockers are plugged
* Score assessment on the leaderboard
	* the score will be computed by evaluating the reconstruction error on a set of different images from the vscan. 
	* @soobash will check the raw data simulation from those images and the reconstruction 
	* then @hackolite can change the leaderboard scoring.
	* @hackolite : total computation time on the leaderboard shouldn’t be over 2 minutes. The image size might be reduced to fulfill this constraint.
	
## 2017.03.08 - HD - 20.00 (Paris time)

### methods 
working week of @aurelie to implement concretely the CapMeth guidelines 
### envelope detection challenge 
new front of the site is available -> css by @jerome_risselin 
docker 4 rabbitMQ & docker 4 django -> bugs currently under investigation by @loic 
@loic : development of functionality to see the source code of any challengers + debugging some password recovery 
proposition of @djalel : ranking challengers by time processing, currently
production scheduled  on monday !

## 2017.03.02 - HD - 20.00 (Paris time)

### Documentation
- @soobash started to draw a detailed scheme of the pipeline for current kit, as well as identifying the bottlenecks
- @aurelie will study the schemes by focusing on missing information for a hypothetical new contributor who would like to jump in the signal processing / hardware
- @soobash pointed the critical importance of fixing the specs (this includes fixing costs) and gather all this information on a single support


### Envelope detection challenge :
- the notebook and leaderboard have been beta-tested.
- @hackolite will add the possibility of downloading other contributor’s codes
- we have to change the way performances of the algorithms are assessed on the leaderboard. Currently, the score is determined by processing the same image as the one being used in the notebook. @soobash will create a set of images + simulated raw data from vscan records. the score will be averaged on this set of images.
- @aurelie will add an introduction to ultrasound imagery principles in the notebook
- integration is in progress. @hackolite is reviewing CSS
- Deadline for launching the challenge : 12/3/17

### Sampling rate tests for ADC :
- @soobash is studying the possibility of using “random” sampling so as to decrease the ADC frequency without losing precision on the signal envelope

## 2017.02.17 - HD - 20.00 (Paris time)
* recap @aurélie : NoteBook updated with some clarifying remarks for the user 
leaderboard site 
* @loic deployed the site here: http://37.187.117.106:8888/
precisely the code for the envelope detection is here: https://github.com/echopen/PRJ-medtec_sigproc/blob/master/echopen-leaderboard/processor_node/uploaded_custom.py 
* @jerome_risselin will work on the css of this site to homogenize it with the current echopen.org stylesheet
* @clement implemented image filters
this is done on the android app: several types of gain filters  
suggests to integrate ITK full featured framework with optimized filters  
* feedback of the testing work of  @jerome, @noureddine and @soobash 
	* test of rotating probe: replaced faulty transducer with old one, tested rotating probe on stationary target in water tank
	* system can do one image per second. system can show target image even 	* without envelope detection 
	* bottle neck is digital envelope detection. Need to speed up the envelope detection code to reach 15 frame per second to have a real-time system
* discussed the signal processing chain and the need to have an onboard DSP
* @all pointed the necessity to get better and more structured informations flow between different groups: embsys, sigproc, androidapp and define clear roadmap and dedicated objectives and related milestones This is the precise the goal of the 11.02.17 CapMeth holding @echOpen

## 2017.02.01 - HD - 20.00 (Paris time)

* feedback, several measures were done @jerome @nourredine @soobash @benjamin 
* jérôme proposal, @clement is currently developing an app android : look-up table/contrast, envelope detection
* V0 & V1 challenge definition @luc : the first and up-coming one consists in getting the best envelope detection, to narrow the spotting and the second, given the transducer specifications, consists in processing the signal in such a way to get the narrowest spot
* Definition of the phantom : we need to design  one out of strip board, we can get luc’s one for testing, consisting in stems
* waiting for @loic’s PR, and @aurelie will give us the go ! on principle kicking the challenge next week ;) 


## 2017.01.25 - HD - 20.00 (Paris time)
### Envelope detection
* NoteBook : 
	* @aurelie cleaned the notebook, and is now prepared to kick-off
	* Notebook is available [here](https://github.com/echopen/PRJ-medtec_sigproc/blob/master/SigProc_101/SigProc-101-pimped.ipynb)
	* @aurelie will explicit a little bit further the submisssion process on the notebook, especially to aware contributors that reconstruction methods are available inside the python notebook 
	* when ready, the challenge will be made public and spread out
* Leaderboard 
	* @hackolite integrated the score scripts, the leaderboard is updated. 	* Submission are now possible by uploading  
	* @hackolite suggests user to stress test the platform and that we can call for contribution to clean some UI part  
	$ discussion about the security breaches when installing libs. Solution @djalel : add a requirements.txt file with all the necessary libs that can be installed using pip. For other libs, submitters should contact the admin.

### Electronics
* @nourredine inspected on 20.01.17 the echOpen’s elctronics and has a whole list of simple improvements, in order to consolidate the electronics consistency. @nourredine stresses the point that we should get precise specs, either for the hardware development or for challenge. All this is convergent and coherent with the importance of a CAPMeth
* @nourredine and @soobash are going to drive bunch of electronics tests in coordination with jerome 


## 2017.01.18 - HD - 20.00 (Paris time)

* presentation of new comers Clement Le Couedic and Mickaël-André
* Discussions about the python notebook and kick-off of the challenge
* @nourredine proposes to check more in depth the electronics. A visit is scheduled on 20.01.17 

## 2017.01.11 - HD - 20.00 (Paris time)

* @luc and @aurelie: produced a python notebook on a envelope detection challenge. For the moment raw data are simulated from images by modulating with a sinusoïdal function, the frequence of which corresponds to the echOpen piezo frequence.
* @aurelie and @luc will add more information about the metrics used
* @luc wants to change the implementation of the Baseline envelope detection function (replace decimation by bicubic interpolation)
* @aurelie and @djalel will complete the notebook to build up a starting kit
python notebook will be pushed on @loic’s server and then kick-off the challenge
* @jerome will produce raw data in the next few days with the help of a calibrated phantom 
* redpitaya code runs now at fast sample rate and needs now optimisation. * @djalel suggests to pass the algo to GPU specialist and challenge him. @loic is working on CUDA and could be interested to work on this challenge. 
* Loïc is adding nbviewer to the challenge platform
* @soobash will document the metrics used for the denoising challenge (docstrings containing simple intuition plus the corresponding formulae)
* @djalel suggests a roadmap for the AI team: 
	* work on the current echOpen images in order to enhance the image quality (potentially using knowledge transfer and Vscan data)
	* start a separate workgroup on organ detection and anomaly detection applied to the other available data (primarily from the AP-HP datalake) 
include the data collection (data repatriation) in the very design of the UX
	* (@mehdi's suggestion) [long term] crowdsource annotations on echOpen images from practitioners.

## 2017.01.04 - HD - 20.00 (Paris time)
* welcoming of a new participant Kevin
* kit/redpitaya image debugging pointed by @luc and @aurelie 
-> strikes appear on images, related to a trigger delay effect. 
* However, @jerome succedeed in a brand new implementation of the kit/redpitaya (using a digital processing filter, instead of the analog filter), getting more data, exploiting the full abilities of the sample rate (125Msps instead of 125/8Msps previously), and the 14 bits precision of the device. Should have the new images in the next days  
* @kevin wants to contribute to phantom 
* @all agree upon the necessity to develop a better signal processing before treating the images - and that the processing needs to be aligned on the implementation of the medical prototype
* So a challenge is proposed in order to make the communities suggest filter from the new kit raw datasets 
*  @luc and @aurelie are going to push a jupyter notebook, to expose the challenge pedagogically and provide synthetic raw data. (this also enables one to understand what was the source of the error with the first set of data acquired in the aquarium).
*  @jerome provides the dataset along with a calibration phantom. The phantom must be sufficiently well calibrated in order to get a gold standard of the output datasets
* @kevin will start playing with algo on raw datasets
* @aurelie suggests to develop an ML approach of a hyper-resolution system -> * @benjamin is going to develop some related compression tool

# 2016

## 2016.12.20 - HD - 20.00 (Paris time)
* running and testing different materials to get images on real devices
* UltraMark device
* echOpen kit
* recent ultrasound device
* echOpen images lacks of contrasts. Addendum : this CR is edited the 23.12.16 and we got a far more image on echOpen’s kit by amplifying the signal : the RAMP is varied from 0.8 to 1, instead of 0 to 1
* The ultrasound phantom is not working properly : only half of the insiders objects appear and appear not as neatly as clearly as it should. Btw, echOpen’s kit seem not to be as performant to detect it.
* acquarium nodejs platform is now all set up : it enables to get ultrasound data from remote, after passing some parameters such as : number of lines, decimation, RAMP values, angle of sector acquisition, number of images. It should be deployed as soon as the team decide to do so ;)
* @aurelie states that denoising echOpen’s images is useless since we do not have as much resolution as would need those type of problematics to emerge. 
* @djalel @aurelie @benjamin was decide to begin playing with real data, so that acquarium datasets have to be released. At the time of writing this post, this was done on the 23.12.16 : with a sponge, a gelpad and @jerome’s hand


## 2016.12.14 - HD - 20.00 (Paris time)

Soobash: work in progress on the metrics to validate the algos, still need images

Aurélie: denoising night in general to the accurate restitution of the outlines

Sami proposes to bring back a V-scan next time, we understand that Echopen must have the precision of the dinosaur

To foresee: a point doctors and interveners along the chain of acquisition (Jerome in particular) to reflect on what is important as characteristics for diagnosis.

In ultrasound, it is mainly the dynamics of the image, the video that is important.

By Saint-Louis, one can recover many videos of V-Scan according to Sami. In addition, they would be annotated.

In Saint-Louis they store a lot of videos, especially since there are not 36000 diagnoses to do.

The basis of the diagnosis is not the image but the video.

## 2016.12.07 - HD - 20.00 (Paris time)

* @noureddine : need for a calibration measurement campaign
* @djalel : need to monitor the phantom to get the first feeling
* @djalel : need to customize NN to the operator behaviors
* objective of 14.12.16 : compare algo of Djalel’s and Benjamin’s algos. The dataset is the kaggle one : ultrasound image of some nerve segmentation
* @noureddine suggests to be aware of the limits of noising artificially the images, because the nature of noise is singular
* we acted to test @benjamin and @djalel’s algo on current implemetation of echOpen’s images dataset 
* @aurelie is going to help finish the redpitaya API to get image datasets from th node interface. @mohammed va épauler @djalel pour le challenge de la semaine prochaine
* @loic split the work with @edem : this way 
	* Investigation Connection * mongondb-django
	* Creation of the data model
	* Metric Resource host: cpu / memory
	* Deployment scripts and update
	* Secure executions:
	* scripts SHA-1
	* analysis of the source
	*capcha
* Improved graphical interface
	- Display detailed info by run
	- Displays images by run
	- Displaying the code for each run
* Automation control of ultrasound
* Production process
* Clean source code

## 2016.12.14 - HD - 20.00 (Paris time)
remark the CR is unsualy short because the main typograph had to leave prematuraly the meeting 

* @nourredine presented a quick sketch of a review of (french) articles
@todo : contact the authors, mainly at Telecom Paris Tech, Poitiers University, etc
* @djalel presented his approach on neural networks

## 2016.11.24 - HD - 20.00 (Paris time)
* Greating point with Aurélie Mutschler, nuclear physics PHD and Mahdi Mohamed, student currently mastering in Ecole Mines Paris Tech 
* @loic : GitBook update, GitHub ticketing on place, needs feedback of challenge web-server installation from Edem
* @djalel @nourredine : mini-course on deep learning approach for denoising images
* @all Brain Storming on the Kind of Noise
	* How to create a noise as close as possible to the ultrasound conditions
From a scientific litterature review, we get a handy formula, that should and will be tested -> it is some logxnormal noises
	* It is discriminated between normal electronic noise vs physical noise
Hence, the question is “how to learn“ ? The process that was agreed on is
		- inject normal noises
		- inject log*normal noises 
		- and acquire aquarium images with moving position, average the signal to get the denoised image
	* It was noticed that the electronic noise is additive vs the physical noise can be reasonably  expected as multiplicative. There will be some challenge around that issue
	* It was noticed that working with a dataset such as kaggle, injecting noise and then train the neural networks could lead to learn the noise itself. This is a point of vigilance
* Upcoming Challenge for the 01.12.16 -> Benjamin vs Djalel : Frequentist vs Deep learning approach
* for the hacker team @luc @benoit @loic : we need to acquire in a week long session ultrasound data with moving target in the aquarium, the several positions should be as precise as possible


## 2016.11.17 - HD - 20.00 (Paris time)

* new incomer Sébastien Tréguer, data-scientist #deep learning, came with a colleague, Jan Schlüter, which is a famous one, he is the developer and maintainer of Lasagne, a famous library in Machine Learning, Neural Networks  (but sorry I didn’t know about that ;))
* Lomé developers were presented to the team because they want to join. The same one are currently deploying a full echOpen instance in Lomé fablab called minodoo. 
* @loic : finished the web platform and working on the net steps are enhancement
* points were raised about the interest of letting people process the metric extraction scripts on their local with advantages of dealing with different development environment, security, not to worry about infra-structure, concurrent processing 
* it was opposed that the idea is to upload algorithms in order to share them publically. But the security concern is a good argument
provide a cluster architecture in case Big Data training is needed or required
* Remark : if the big data cluster appear not be needed, which tends not to be the case, a complementary solution could emerge for further developments and scripts could be processed locally, denoised images could be sent together with the raw source file of the algorithms
* it is scheduled to implement a data architecture for the probe in the acquarium : the idea is to let the acquire data on regular interval of time, and the average of the acquisition will be a correct sample of denoised images. 
* implement the resource metrics CPU, mem and document on GitBook 
* @benjamin is working on a denoising algo with a statistical approach , will finish the implementation for next week and document on GitBook the SigProc metrics choice explanation
* @djalel is working on a neural network to denoise images through neurla networks, from artificially, will finish the implementation for next week
* @nourredine kicks off a discussion about the noise structure, and suggests to act on noise as soon as possible. A coordination with the electronics team will be scheduled as soon as the hardware is set up. 
The idea is that acting twice both on signal and image denoising could lead to images hard to analyse for the doctors 
It was opposed that signal treatment will be quite simple, mainly envelope extraction and not the phase extraction, which limits the possibility to act at this step. Second, the machine learning will be done on the basis of the image datasets we want to access to. Indeed, the image provider, namely APHP, serves medical imagery devices images and not raw signals

## 2016.11.10 - HD - 20.00 (Paris time)

* Annonce d’un nouvel arrivé dans la team Signal Processing : Mohamed Mahdi, polytechnicien de tunis,en ce moment à l’école des Mines, spécialité Robotique & Traitement du Signal
* @benjamin + @djalel : travail sur 1 réseau de neurones pour débruitage d’images echo à partir de bruits artificiels. 
* @benj rapporte que les algo à l’usage sont aujourd’hui spécifiques des organes explorés. 1 point particulier est relevé autour d’1 algo autour de la carotide et qui est particulièrement efficace 
* @djalel propose d’universaliser les approches par du deep learning  
* @Loic a terminé la plate-forme d’upload d’algo, d’extraction des metrics d’update de leadrboard. Accessible ICI
* prez du code du RAMP, Rapid Analytics and Model Prediction proche de ce que @Loic a fait 
	* @djalel était un des commiters. 
	* @djalel fait état des besoins d’installation de Tensor Flow, @Loic est dessus
* proposition de loic d’utiliser un sys. de ticketing, sans doute celui de github, car nous commençons à être nombreux;)

## 2016.10.27 - HD - 20.00 (Paris time)

* proposition par Soobash d'un score pour le ranking du leaderboard + discussion sur l'adaptation des métriques de frames d'images
* évolution de l'interface leaderboard par @hackolite @todo : adaptation de l'algo pour calculer les métriques sur une séquence image, plutôt qu'une image tel que c'est le cas aujourd'hui
* présentation par @benjamin d'une méthode d'injection sur images de bruit spécifique à l'écho. @todo : implémentation d'un premier réseau de neurones pour débruiter des images;)

## 2016.10.19 - HD - 20.00 (Paris time)

* discussion du Challenge online qui sera lancée dès que tout est prêt
interface web, django app, de récupération, d'analyse des soumissions, et de leaderboard achevée thanks @loic;)  @todo :  analyse non d'une image mais d'une boucle d'images + système de login
* scripts de métriques des soumissions terminés thanks Soobash;) @todo constituer les métriques qui nous sont propres
* demeure la question de l'analyse de la typologie de bruit en vue de pouvoir l'injecter à des "images saines" à des fins d'apprentissage. C @benjamin qui s'y colle pour la semaine pro thanks;)

## 2016.10.12 - HD - 20.00 (Paris time)

* Présentation de Nourredine Ellouze, ancien dir. de recherche en traitement du signal, avec une focale sur le denoising + ingénieur électrique + plein de choses 
* Plate-forme web : achever la plate-forme d'upload/extraction des métriques des algorithmes de débruitage + branchement de la sonde dans l'acquarium
Challenge : monter un challenge à partir de datasets, soit existant & accessibles via un récent challenge de Kaggle, soit à partir des data d'echOpen 
* Algo 
	* quel spécificité du bruit échographique ? savoir reproduire artificiellement le bruit pour les injecter dans les images -> priorité de la semaine qui vient 
	* les reverse engineerer par réseaux de neurones. A ce titre, Djalel, animateur du groupe IA d'echOpen était présent, car important de maintenir une articulation entre le groupe `Image processing` et le groupe `IA` et a donné des pistes de travail : débruitage, compression du signal
* Au plan pratique, les membres du groupe choisissent de se retrouver tous les jeudis à compter du 27.10.16. Mais semaine pro, la réu a bien lieu un mercredi, soit le 19.10.16

## 2016.10.05 - HD - 20.00 (Paris time)

* Soobash continue de scripter les métriques, mais on en a l'essentiel 

* loic a packagé le script de récupération des algo et d'extraction des métriques selon les scripts de soobash

* l'arcghitecture pour le contributeur évolue dans le sens suivant 
	* l'espace ide collaboratif (cloud9) permet d'exposer et de jouer avec les codes des contributeurs et leurs libs
	* une interface web/python notebook : avec un "how to" pour package un algo python et qui permet de le soumettre. Le contributeur fait le choix de son environnement de dev et garde ainsi toutes ses routines
nous processons le package, extrayons les métriques et updatons le leaderboard
* Au total, on est prêt dans 2 ou 3 semaines. 
* le bottle neck est la mise en route de l'acquisition dans l'acquarium, idéalement avec fantômes (rdv à ce sujet dans 2 semaines avec medicalem pour livraison d'un fantôme carotidien). 

## 2016.09.08 - HD - 20.00 (Paris time)

* sortie des premiers scripts et métriques. pour les spécialistes, il s'agit calcul  de mse, rmse, ssim -> en cours pour la semaine prochaine
* loic commence à updater la boucle de soumission en ajoutant le calcul des précédentes métriques dans son workflow
* soobash finit les scripts relatifs aux calculs de 6 métriques complémentaires
* benjamin fait une review de "Despeckle filtering for ultrasound imaging and video, Vol. I: Algorithms and software" , notamment pour explorer les techniques statistiques à l'usage en débruitage
