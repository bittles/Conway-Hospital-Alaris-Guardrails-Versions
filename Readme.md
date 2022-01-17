# Conway-Hospital-Alaris-Guardrails-Versions

## 22is:
	add robaxin IV

## 21is:
	add glucagon drip
	
## 20is:
	increase hard max for propofol for seizures
		100 to 200 mcg/kg/min
	phenobarb
		add weight based dose from anti-convulsant protocol
		add basic concentration limits
	add cefiderocol mg and gm
	add premixed peng 3 million units
	add zidovudine
	
	** to do
	seperate therapy for propofol for seizures and sedation?
	check what plan with versed is, baxter or alaris pumps

## 19is:
	added phenobarbital
	add new premix vancomycin concentrations
	double check phenobarbital
	add injectafer weight based
	add bamlaniviab/estesivimab entries for all volumes

	check injectafer catalog code interop (done, no change)
	add tociluzumab

	**to do
	
	add leveteracetam gram option?
	add bam/este mapping
	add anticonvulsant protocol
	add valproate grams?

## 18is:
	added regeneron catalog code to casirivimab/imdevimab
	removed imdevimab/casirivimab
	add 1200mg/260mL concentration and wildcard concentration for different volume bags now possible to regeneron
	renamed crotalidae (Crofab) to antivenin crotalidae
	add anavip catalog code 2749465 (same as crofab no change)
	add 4,6,10 unit concentrations to crotalidae
	add therapies to crotalidae
	rename crofab advisory
	change maxes for crotalidae
	lower leveteracetam soft min to 6 min (999 ml/hr rate for 100 mL bag)

## 17i and 17is:
	mirrored libraries with same changes, difference being 17is has syringe pump capability and drugs in nursery profile
	enabled syringe module use
	built syringe library into nursery profile generally coping from pharmguard/medfusion (old syringe pump library) *****NEEDS CHECKED, checked 3/24/21
		- adjusted min/max weight based dosing slightly with updated recommendations
		- rocephin changed to administer over no less than 60 min due to bilirubin encephalopathy risk
	added imdevimab/casirivimab as well as casirivimab/imdevimab to make it easy to find, set up for new EUA
	added catalog codes to all drugs and concentration aliases and cleaned up alternate entries used in other hospitals but not here, no change to pump front end
		future proof for new drugs if they need to be added and for if/when PCA modules get used
	increased soft max for zerbaxa, had added 3 gm for PNA but never increased soft max
	changed bamlanivimab volume from 200 ml to 270 ml for updated label

## 16i:
	add adenosine drip for cath lab
	add bamlanivimab in preparation for EUA

## 15i:
	add protonix drip 40 mg/100 ml contiunous
	disabled 40 mg/100 ml intermittent to prevent confusion
	add initial infusion default rate to cangrelor for cath lab
	bivalrudin renal dose CrCl cutoff defined as < 30
	tirofiban low dose removed, high dose language removed from therapy names but unchanged
	added 800mg fluconazole
	add 100mg/230ml and 200mg/210ml to remdesivir to make interop work with powder
	added ESRD therapy to bivalrudin, with 250mg/250ml bag.  
	add gm and mg therapies to TXA, change hard min infusion to 7 min
	add 1 g/100 ml conc to TXA, hard min 10 min.  remove volume in calculation of total volume for TXA vial in formulary manager

## 14i:
	change heparin standard/cardiac/PVD from 15 unit/kg/h to 12 unit/kg/h
	cleaned up continuous heparin; removed non weight based therapy; made sure all had heparin advisory
	added actual choices for 3g zerbaxa in guardrails to more easily select it instead of manually putting in strength/volume if not using interop
	added larger size of phenylephrine drip, 40 mg/1000 mL
	added remdesivir, vabomere

		Carefusion analytics reviewed:
	fixed phenylephrine ANES concentration limits.  drug in mg/ml, rate in mcg/min.  conc. limits were set by mcg/ml instead of the assumed mg/ml
	fixed rocuronium, same issue
	fixed vecuronium, same issue
	pancuronium, same issue
	atracurium, same issue
	all continuous checked and concentration limits should be correct now
	added some flexibility to amiodarone rate to lessen alerts (0.5 mg/min min lowered to 0.49 to avoid alerts for 0.498 mg/min)
	dopamine min lowered for same reason
	increassed insulin soft max to show max value on form, hard max unchanged
	norepinephrine limits reviewed, unchanged despite alerts due to form/protocol
	propofol reviewed and reached the same conclusion
	dacarbazine conc. limits reviewed, max increased
	paclitaxel reviewed, no change despite alerts. studies suggest 0.3 mg/ml min dilution 
	daptomycin max dose increased to match new dosing recommendations
	added buffer to max dose of weight based acyclovir (10 to 10.5 mg/kg)
	added non weight based daptomycin for interop use for when osmanzai decides to not order a weight based dose

## 13i:
	"enabled" cardene concentration; was previously created but not active

## 12i,
	added cardene 40mg/200ml conc., amiodarone 360mg/200ml
	updated zerbaxa conc. max limits for gram and mg for new PNA guidelines

## 11i,
	Merrem 2g/50ml removed, conc. limit is 20mg/ml
		add tylenol IV for gram
	add F flag to MVI, MVI+FOLATE+THIAMINE, dextrose 10%, and parenteral nutrition aliases to catch if ordered continuous or intermittent (hopefully)
	add intermittent sodium bicarb to sodium bicarb fluids
	add calcium chloride
	added double volume phenylephrine
	fixed total volume for phenylephrine to account for vial volume
	added double volume for nicardipine
	add 5/50 and 10/100 ivig concentrations
	add 100mg/100ml cardizem
	add infusion center profile and chemo drugs

	TODO:
	bolus for lidocaine drip?? i think worth adding, no policy against

## 10 & 10i,
	Amphotericin B and amphotericin B liposomal changed to primary only
	MVI Only and MVI+Folate+Thiamine moved to fluids libary to allow interop
	Added 15 mEq/L therapy to IVF + KCL
	potassium chloride Increase soft max duration for intermittent (doubled, 10: 3h; 20: 4h; 40: 6h; __: 6h) and daptomycin (1h to 2h) 
	daptomycin; Deleted non-weight based forced via mapping file to WB checking
	Hard max for daptomycin at 12 mg/kg
	Milrinone fixed to the correct concentration
	Acyclovir weight based added
	aztreonam, ceftaroline, calcium gluconat emg and gm dosing added to 
	acetylcysteine Removed blank mg dosing option from 2nd dose > 100kg
	desmopressinadd non weight based dosing to 
	vancomycinadded weight based 
	pralidoxime added gm dosing for 
		Change alteplase and cathflo entries to --> alteplase - stroke & alteplase - non-stroke
	thiamine lowered soft min concentration
	valproic acidadded weight based 
	tobramycin changed to weight based only
	ceftazidime pediatrics hard and soft max adjusted
	epinephrine, insulin, lidocaine, nitroglycerin, norepinephrinepeds drips units changed to match adult units, 
	procainamide removed from peds library
	increased max VTBI for peds and nursery libraries for interop to be able to match larger volume bags
	desmopressin  increased dose limits for weight based
	deferoxamine added weight based setup
	amikacin hard max removed, was 11.5 mg/kg
	cisatracurium, changed aliases to continuous, made standard concentration 200mg/250ml. removed bolus, lowered soft and hard max
	calcium gluconate, removed soft max for both mg and g dosing and left hard max. was causing issues when adding vol of additive to diluent
	chloramphenicol, increased soft max duration limit
	aztreonam, soft min infusion limit for 2g decreased to match other strengths based on lexi/package inserts
	ferric carboxymaltose soft max duration limit increased
	valproate acid removed hard max in peds
	caffeine citrate soft max conc. increased
	micafungin, pediatrics, concen max increased
	metronidazole soft min duration limit decreased
	ampicillin pediatric wt based max dose increased


		POSSIBLE WB ONLY GUARDRAILS:
	Amphotericin B & liposomal

		POSSIBLE NWB ONLY GUARDRAILS:

		BOLUS/LOADING DOSE:
	Aggrastat possible?

## 9 & 9i, Interopability start with Cerner; Show aliases option activated in Guardrails for 9i; from now on, changes to library need to be made in both the regular and interoperability versions
	Caffeine citrate removed, caffeine and sodium benzoate added (to adult library as well as peds)
	Added Avycaz to adult library as ceftazidime/avibacta
	Added pentamidine and chlorpromazine and pralidoxime
	Mannitol in fluid library deprecated as duplicate from intermittent library
	Therapy added for Cathflo, DVT/Ischemic limb with base concentration and limits to match protocol
	Clindamycin vials changed in Cerner formula to not add to volume to simplify pump entries; changed from base concentration in pump library to individual dosages (ie. 300mg, 600mg, 900mg); safer and easier for nurses
	Changed initial zosyn infusion time for 4.5g, was 4:00, now blank
	Combine PPN and TPN to Parenteral Nutrition
	.IVF + KCL entry added with 4 therapies, 10 mEq/L, 20 mEq/L, 30 mEq/L, 40 mEq/L; this in addition to seperate entries for .IVF + KCL xx mEq entries, premixed bags mapped to seperate entries while vial mapped to entry with seperate therapies
	Duplicate entry for banana bag entries that exist now are 'MVI Only' and 'MVI+Folate+Thiamine'
	Tirofiban (Aggrastat) added therapies and some therapies renamed: 'HiDose & CrCl < 60', 'HiDose & CrCl >= 60', 'LoDose & < 153 kg', 'LoDose & >= 153 kg', 'LoDose,Renal &<153kg', 'LoDose,Renal&>=153kg'
	Sodium phosphate updated to fit DKA protocol
	Clinical Advisory for TPN fluid entry only on adult profile was incorrect, fixed to be the correct warning about infusions in a midline catheter
	.mg and gm dosing therapies added to aminocaproic acid to cover in the event its ordered in grams in interop
	amiodarone removed from pediatric library (no hospital protocol to follow for this patient population)
	aztreonam had 2 g/50 ml concentration added due to a premixed bag we carry
	Mannitol 20 % free concentration removed, only 100 gm / 500 ml bag left, vials are 25 %
	Min infusion times increased for Cathflo (1 to 7 min), ceftaroline (5 to 7 min), hetastarch (30 to 31 min), ibutilide (4 to 7 min), and mannitol (25 to 31 min) to prevent pump from trying to program above 999 ml/hr
	Minor changes to hard max dose limits (~10-15% increase) on some drugs to accomodat interoperability, should be no effect on regular workflow
	Vecuronium ANES deprecated, blank mg / mL setup added to regular vecuronium entry marked anesthesia only; basically just combining these two entries, no functionality lost

	Added double strength double volume precedex
	removed oxytocin - induction hard limits
	adjusted cisatracurium limits on concentration
	zosyn mg therapy added to peds library in 9i for interop, weight based therapy added as well
	removed bolus from alteplase, fixed concentration to coincide with stroke order set

		TODO:	
	build fluid bolus entries in intermittent library, or is it continuous??

		DONE:
	Check on if Ryanodex needs to be added and/or generic dantrolene needs to be removed
			UPDATE: Ryanodex has same admin instructions as other dantrolene products, no need to change anything
	Possibly alteplase.  Cannot exist in current form with interoperability, might need to be out of scope
			UPDATE: alteplase should work in scope, check if ER is using bolus on pump or pulling out bolus with syringe

## 8, Bolus feature removed from diltiazem drips
	changes to occlusion configurations under Pump Module Configuration
	Changed naming for pantoprazole, from 'pantoprazole' to 'pantoprazole gtt' avoid confusion
	Auto-Restart Attempts changed in configuration for Adults and Peds library from 5-->>9
	IVF + oxytocin removed
	'Folic Acid' capitalizations were removed so the entry is just 'folic acid' to be more in line with other entries
	MVI (only vitamins) and MVI(folate+thiamine) added as intermittent options
	Removing IVF + Vitamins from Fluids
	Oxytocin conversion chart made for OB for mL to unit in order to easily access for bolus
	Oxytocin min and max bolus values changed to allow boluses from 1 to 30

## 7, Ketamine ANES added, initial 0.1 mg/kg/hr, soft max 0.5 mg/kg/hr, hard max 1 mg/kg/hr
		Concentrations of 50mg/50ml and 100mg/100ml added until can be narrowed
	Propofol ANES given bolus range of 19-71 mg, initial 30 mg (3 mL); Bolus is 12 mL/min
	zz Code drugs fixed to match their non-zz counterparts

## 6, Oxytocin blank setup removed, entries added under postparum for 10, 20, 30, 40 units in 1000 ml; GO LIVE DATASET

## 5, Post-"finalized" data set, pre-go live
	Double concentrated therapies added for dopamine, dobutamine, norepinephrine, and vasopressin
	Dobutamine Echo Stress therapy added
	Bug fixes and stability improvements
	Added blank setup for oxytocin postpartum with conc. limits

## 4, Finalized data set with changes from data set analysis
	Library nomenclature changed from eg. cmc.pump.library.yyyy.x to conwaymedical.yyyy.x where x is version number
	Typos found during data set anaylsis fixed
	Mins set for every drug
	Concentration limits set for every drug
	Approved and released and uploaded for training
	Fixed a bug that allowed concentrations to shadow-step to unintended locations
	Bug fixes and stability improvements

## 3: Data Set Review Changes
	Kinevac added
	Dobutamine stress test therapy
	Anesthesia drugs reviewed
	Maternity insulin fixed
	Bug fixes and stability improvements

## 2: Data Set for Data Set Review
	"Completed" library, entries for majority of drugs

## 1: Initial Drug Library