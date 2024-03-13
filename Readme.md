# Conway-Hospital-Alaris-Guardrails-Versions
## Format is "version # and activated go-live date"

### MAPPING FILE CHANGES NOT LIVE (Nick 3/13/24)                                in file Mapping_File - NEXT_VERSION.xlsx
  #### added Clinimix 4.25/5 with and w/o additives to mapping file   (mapped to alias 1000000001 (Parenteral Nutrition, fluid))
    ##### no changes needed to guardrails data set for this
  #### added regular insuliin in NS to specify an alias for regular insulin drip to differentiate from insulin maternity  (mapped to alias 1000000200 (insulin, continuous))
    ##### WHENEVER THIS MAPPING FILE GOES LIVE, GUARDRAILS DATA SET ALIAS FOR INSULIN (in master drug list) WILL NEED UPDATED FOR ALL CONCENTRATIONS TO 1000000200C
  #### added regular insulin in D5NS to specify an alias for insulin maternity to differentiate from regular insulin   (mapped to alias 1000000201 (Insulin Maternity, fluid))
    ##### WHENEVER THIS MAPPING FILE GOES LIVE, GUARDRAILS DATA SET ALIAS FOR INSULIN (in master fluid list) WILL NEED UPDATED TO 1000000201F

## 67is xx/xx/24:

## 66is 02/14/24:
  ### risankizumab:
    - add to outpt infusion library
    - 600 mg/110 mL, 600 mg/260 mL, 600 mg/510 mL
    - duration limits:
      - initial: 01:00
      - soft max: 04:00
      - hard min 00:55
    - dose limits:
      - soft min: 550 mg
      - soft max: 650 mg
      - hard max: 660 mg
  ### deferoxamine:
    - add to onc infusion library
    - 1000 mg/1000 mL, 1 g/1000 mL
    - duration limits:
      - initial: 03:00
      - soft max: 24:00
      - soft min: 01:00
    - dose limits:
      - soft min 900 mg / 0.9 g
      - soft max 1100 mg / 1.1 g
  ### ertapenem:
    - add to pediatrics library
    - two therapies:
      - Weight <= 33 kg:
        - Wildcard x mg/x mL
        - Weight bosed dose limits:
          - soft min: 5 mg/kg
          - hard max: 15.1 mg/kg
        - Concentration based limits:
          - hard minL 1.4 mg/mL
          - soft min: 1.46 mg/mL   (9.8 kg, the lower limit for non-syringe antibiotics for peds, at 15 mg/kg is 147 mg and in 100 mL is 1.47 mg/mL)
          - soft max: 20.1 mg/mL  (1000 mg/50 mL = 20 mg/mL)
      - Weight > 33 kg:
        - 500 mg/50 mL, 500 mg/100 mL, 1000 mg/50 mL, 1000 mg/100 mL
    - Duration limits:
      - initial: 00:30
      - hard min: 00:28
      - soft max: 06:00

## 65is 02/02/24:
  ### dextrose 12.5%:
    - added to nursery library under fluids with same limits as D10%

## 64is 01/29/24:
  ### ado-trastuzumab:
    - added to onc infusion library
    - weight based dose limits:
      - soft min: 2.25 mg/kg
      - soft max: 3.9 mg/kg
      - hard max: 4 mg/kg
    - duration limits:
      - hard min: 00:28
      - soft min: 00:29
      - soft max: 02:00
      - no initial
    - concentration limits:
      - hard min 0.3 mg/mL
      - soft min 0.4 mg/mL
      - soft max 3.6 mg/mL
    - advisory: 0.22 micron in line filter needed for admin
  ### protamine:
    - added to adult library
    - dose limits:
      - soft min: 0.4 mg
      - hard max: 50 mg
    - duration limits:
      - hard min: 00:05
      - soft max: 01:00
      - initial: 00:10
    - concentration limits:
      - hard min: 0.004 mg/mL (allows for unlikely but possible 0.5 mg in 100 mL)
      - soft max: 1.11 mg/mL (50 mg/5 mL of drug in 50 mL bag for 50 mg/55 mL total volume is 1.1 mg/mL)

## 63is 01/22/24:
  ### enfortumab vedotin:
    - add to oncology infusion library
    - 2 therapies
    - wt <= 100 kg
      - soft min: 0.4 mg/kg
      - soft max: 1.25 mg/kg
      - hard max: 1.3 mg/kg
    - wt > 100 kg
      - soft min: 49 mg
      - soft max: 125 mg
      - hard max: 125.1 mg
    - duration limits:
      - hard min: 00:27
      - soft min: 0028
      - soft max: 04:00
      - initial: 00:30
    - concentration limits:
      - hard min: 0.29 mg/mL
      - soft min: 0.3 mg/mL
      - soft max: 4 mg/mL
  ### fosaprepitant:
    - change 150 mg/150 mL concentration entry to 150 mg/250 mL
  ### dexamethasone:
    - only changes to oncology infusion library:
    - set concentration limits:
      - hard min: 0.008 mg/mL
      - soft min: 0.009 mg/mL
      - soft max: 0.4 mg/mL

## 62is 01/16/24:
  ### tocilizumab:
    - change from primary only to primary and secondary to allow to hang bag for flushing
    - add clinical advisory: Dedicated IV Line: Do not infuse any other drugs through this line.
  ### iron sucrose:
    - add to pediatrics library with 2 therapies
      - .mg, pt wt <40kg; .mg, pt weight >=40 mg
    - .mg, pt wt <40kg:
      - weight based
      - dosages:
        - soft min: 0.4 mg/kg
        - soft max: 7 mg/kg
        - hard max: 7.3 mg/kg
      - durations:
        - hard min: 00:29
        - soft min: 00:30
        - soft max: 1:35
      - concentration limits:
        - hard min: 0.9 mg/mL
        - soft min: 1 mg/mL
        - soft max: 2 mg/mL
    - .mg, pt weight >=40 mg
      - dosages and durations:
        - 100 mg/105 mL and 100 mg/55 mL
          - hard min: 00:29
          - soft min: 00:30
          - soft max: 2:00
          - initial: 00:30
        - 200 mg/110 mL
          - hard min: 00:55
          - soft min: 00:57
          - soft max: 3:00
          - initial: 1:00
        - 300 mg/265 mL
          - hard min: 1:20
          - soft min: 1:25
          - soft max: 4:00
          - initial: 1:30
  ### Trabectedin:
    - add to onc infusion library
    - clinical advisory: 0.22 micron in-line  low protein binding filter needed
    - dosage limits:
      - soft min: 0.2 mg/m2
      - soft max: 1.15 mg/m2
      - hard max: 1.2 mg/m2
    - concentration limits:
      - no hard min
      - soft min: 0.001 mg/mL
      - soft max: 0.01 mg/mL
    - durations:
      - hard min: 02:45
      - soft min: 02:50
      - soft max: 04:00
      - initial: 03:00
  ### Polatuzumab Vedotin:
    - add to onc infusion library with wildcard concentration
    - clinical advisory: 0.22 micron in-line filter needed
    - dosages:
      - soft min: 0.9 mg/kg
      - soft max: 1.98 mg/kg
      - hard max: 2 mg/kg
    - concentration limits:
      - hard min: 0.71 mg/kg
      - soft min: 0.72 mg/kg
      - soft max: 2.71 mg/kg
    - durations:
      - hard min: 00:29
      - soft min: 00:30
      - soft max: 03:00
      - no initial
  ### pemetrexed:
    - lower soft min dose from 250 mg/m2 to 240 mg/m2 for rounding
    - adjust hard max from 900 mg/m2 to 910 mg/m2
  ### Crizanlizumab:
    - add to onc infusion center
    - clinical advisory: Use a 0.22 micron in-line filter when administering this product.
    - wildcard weight based concentration
    - dose limit:
      - soft min 4.5 mg/kg
      - soft max 5.5 mg/kg
      - hard max 5.51 mg/kg
    - concentration limits:
      - hard min 1 mg/mL
      - soft min 2 mg/mL
      - soft max 5 mg/mL
    - duration limits:
      - hard min 00:27
      - soft min 00:28
      - soft max 04:30
      - initial 00:30

## 61is 01/04/24:
  ### Adult library drugs with any changes (see alphabetical list of drug entries below library summary for details on changes):
    - albumin 25%
    - amikacin
    - amphotericin B liposomal
    - avibactam/ceftazidim
    - ceftriaxone
    - daptomycin
    - ferumoxytol
    - immune globulin
    - mag sulfate
    - methylprednisolone
    - micafungin
    - piperacillin/tazobactam
    - potassium chloride
    - tocilizumab
    - vancomycin
    - zoledronic acid
  ### Adult library drugs reviewed with no changes:
    - ceftazidime
    - dalbavancin
    - ertapenem
    - iron sucrose
  ### OutPt InfusionCenter new drugs:
    - ceftazidime
    - meropenem
    - micafungin
    - oritavancin
    - piperacillin/tazobactam
    - potassium chloride
    - spesolimumab
    - ustekinumab
  ### OutPt InfusionCenter with any changes (see alphabetical list of drug entries below library summary for details on changes)
    - abatacept
    - albumin 25%
    - amphotericin B liposomal
    - amikacin
    - belimumab
    - ceftriaxone
    - dalbavancin
    - daptomycin
    - ferumoxytol
    - immune globulin
    - methylprednisolone
    - mag sulfate
    - ocrelizumab
    - tocilizumab
    - vancomycin
    - vedolizumab
    - zoledronic acid
  ### OutPt InfusionCenter library drugs reviewed with no changes:
    - bezlotoxumab
    - ertapenem
    - golimumab
    - iron sucrose
    - teprotumumab
  ### ONC Infusion Center new drugs:
    - decitabine
    - durvalumab
  ### Pediatrics library drugs with changes:
    - albumin 25%

  ### abatacept:
    - reviewed outpt infusion library
    - add weight based dosing for GVHD and covid
  ### albumin 25%:
    - reviewed adult, pediatric, and outpt infusion libraries
    - add 5 g/20 mL concentration
      - durations:
        - initial: 0:20
        - soft max: 1:00
        - soft min: 0:08
    - dose limits updated:
      - soft min: changed from 12.5 g to 4.9 g
  ### amphotericin B liposomal:
    - reviewed adult and outpt infusion libraries
    - dose limits adjusted after review:
      - soft min decreased from 2 to 1.9 mg/kg to account for rounding
      - soft max increased from 7 to 10.5 mg/kg for mucormycosis dosing
    - clinical advisory updated changing the wording from required use of in-line filter to may use an in-line filter >= 1 micron
    - concentration limits updated:
      - hard min increased from 0.1 mg/mL to 0.8 mg/mL
      - soft min increased from 0.2 mg/mL to 0.9 mg/mL
      - soft max increased from 2 to 2.1 mg/mL
  ### amikacin:
    - reviewed adult and outpt infusion libraries
    - hard max increased from 31 mg/kg to 39 mg/kg for cystic fibrosis dosing (~10% buffer)
  ### avibactam/ceftazidim:
    - renamed from ceftazidime/avibacta
    - reviewed adult library
    - changed soft max from 2:18 to 3:20 as there's some dosing on administering over 3 hr
  ### belimumab:
    - reviewed outpt infusion library
    - minor adjustments to concentration limits otherwise no changes
  ### bezlotoxumab:
    - reviewed outpt infusion library, no changes
  ### ceftazidime:
    - add to outpt infusion library with same guardrails as adult
    - 1 g/50 mL, 1 g/100 mL, 2 g/50 mL, 2 g/100 mL, 1000 mg/50 mL, 1000 mg/100 mL, 2000 mg/50 mL, 2000 mg/100 mL
    - soft min 0.25 g (and 250 mg)
    - soft max 2 g (and 2000 mg)
    - initial 0:30
    - soft max 1:00
    - soft min 0:15
    - add 500 mg/50 mL, 500 mg/100 mL, 0.5 g/50 mL, 0.5 g/100 mL to adult and outpt infusion libraries
    - reviewed dosage and administration guardrails for adult library as well
  ### ceftriaxone:
    - reviewed adult and outpt infusion libraries
    - very minor updates to dose and concentration limits
  ### dalbavancin:
    - reviewed adult and outpt infusion libraries
    - outpt infusion library updated to match options from adult library
  ### daptomycin:
    - reviewed adult and outpt infusion library
    - soft max increased from 10.5 mg/kg to 12.1 mg/kg for VRE bacteremia
    - minor adjustments to concentration limits
    - outpt infusion updated to be on par with adult library
  ### durvalumab:
    - add to onc infusion library
    - 1500 mg/280 mL and wildcard x mg/x mL concentrations
    - two therapies: >= 30 kg, and < 30 kg
    - durations for both therapies:
      - initial: 1:00
      - soft max: 8:00
      - soft min: 0:55
    - concentration limits:
      - soft min 1 mg/mL
      - soft max 15 mg/mL
    - >=30 kg
      - 1500 mg/280 mL
      - soft min: 1499 mg
      - soft max: 1501 mg
    - < 30 kg
      - x mg/x mL weight based dosing
      - soft min: 9 mg/kg
      - soft max: 21 mg/kg
    - primary only
    - Advisory: This medication must be infused using a 0.2- micron, low protein binding filter.
  ### ertapenem:
    - reviewed outpt infusion and adult libraries, no changes
  ### ferumoxytol:
    - reviewed outpt infusion and adult libraries
    - add advisory: Risk of hypersensitivity.  Check vital signs frequently during infusion.
  ### golimumab:
    - reviewed outpt infusion library, no changes
  ### immune globulin:
    - reviewed outpt infusion and adult libraries
    - remove wildcard, 5 g/100 mL, and 10 g/200 mL concentrations
  ### iron sucrose:
    - reviewed outpt infusion and adult libraries, no changes
  ### meropenem:
    - add to outpt infusion library
    - 500 mg/50 mL, 500 mg/100 mL, 1000 mg/50 mL, 1000 mg/100 mL, 2000 mg/100 mL
    - 0.5 g/50 mL, 0.5 g/100 mL, 1 g/50 mL, 1 g/100 mL, 2 g/100 mL
    - durations:
      - initial: 0:30
      - soft max: 3:10
      - soft min: 0:15
    - reviewed dosage and administration guardrails for adult library as well
  ### methylprednisolone:
    - reviewed outpt infusion and adult libraries
    - add options for 500 mg/50 mL and 1000 mg/50 mL as stability allows it and allow possible future scenarios with 100 mL snap bags on back-order
  ### micafungin:
    - add to outpt infusion library
    - 50 mg/100 mL, 100 mg/100 mL, 150 mg/100 mL
    - durations:
      - initial: 1:00
      - soft min: 0:55
      - soft max: 3:00
    - reviewed dosage and administration guardrails for adult library as well
    - extend soft max for adult library from 1:30 to 3:00 as can be infused slower to minimize infusion related reactions
  ### mag sulfate:
    - reviewed outpt infusion and adult libraries
    - add 1 g/100 mL premixed bag concentration to both libraries
    - add 2 g/50 mL, 4 g/100 mL, and wildcard concentration from adult library to outpt infusion
  ### ocrelizumab:
    - reviewed outpt infusion library
    - changed concentrations from 300 mg/250 mL and 600 mg/500 mL to 300 mg/260 mL and 600 mg/520 mL, respectively, to account for drug volume
  ### oritavancin:
    - add to outpt infusion library
    - 4 therapies options: Kimsyra mg, Kimsyra gram, Orbactiv mg, Orbactiv gram
    - 1199 mg (1.199 g) soft min for both brands
    - 1201 mg (1.201 g) hard max for both brands
    - Kimsyra: 1200 mg/250 mL, 1.2 g/250 mL
      - 1:00 initial
      - 1:15 soft max
      - 0:55 hard min
      - Advisory:  If a common IV line is being used to administer other drugs in addition to oritavancin, the line should be flushed before and after each infusion with D5W or NS.
    - Orbactiv: 1200 mg/1000 mL, 1.2 g/1000 mL
      - 3:00 initial
      - 3:30 soft max
      - 2:45 hard min
      - Advisory: If a common IV line is being used to administer other drugs in addition to oritavancin, the line should be flushed before and after each infusion with D5W.
  ### piperacillin/tazobactam:
    - add to outpt infusion library
    - 3.375 g/50 mL, 3.375 g/100 mL, 4.5 g/50 mL, 4.5 g 100 mL
    - duration limits:
      - no initial
      - soft max: 4:15
      - soft min: 0:20
    - dose limits:
      - soft min: 3 g
      - hard max: 4.6 g
    - reviewed dosage and administration guardrails for adult library as well, concentrations and durations updated to match above guardrails (except initial rate for 3.375 g set to 4:00)
  ### potassium chloride:
    - add to outpt infusion library
    - 10 mEq/100 mL, 40 mEq/520 mL, x mg/x mL
    - dose limits:
      - soft min: 5 mEq
      - hard max: 41 mEq
    - concentration limits:
      - hard min: 0.04 mEq/mL
      - soft min: 0.07 mEq/mL
      - soft max: 0.11 mEq/mL
    - duration limits:
      - 10 mEq/100 mL:
        - initial: 1:00
        - soft max: 6:00
        - soft min: 0:45
        - hard min: 0:25
      - 40 mEq/520 mL:
        - initial: 4:00
        - soft max: 12:00
        - hard min: 3:15
      x mEq/x mL:
        - no initial
        - soft max: 12:00
        - soft min: 1:45
        - hard min: 0:50
    - reviewed dosage and administration guardrails for adult library as well, concentrations and durations updated for peripheral line to match above guardrails
  ### spesolimumab:
    - add to outpt infusion library
    - 900 mg/100 mL
    - 1:30 initial default duration
    - 1:25 soft min
    - 3:00 soft max
    - 899 mg dosage soft min
    - 901 mg dosage hard max
    - primary only
    - Advisory: This medication must be infused using a 0.2- micron, low protein binding filter.
  ### teprotumumab:
    - reviewed outpt infusion library, no changes
  ### tocilizumab:
    - reviewed dose and administrations guardrails for outpt infusion library and adult library
    - concentration limits slightly adjusted
      - hard min: 1 mg/mL   (allowing for extremely unlikely 20 kg patient dosed at 4 mg/kg, i.e. 80 mg, made in 50 mL)
      - soft min: 1.1 mg/mL
      - soft max: 8.1 mg/mL  (800 mg being max dose prepared in 100 mL)
    - 2 options:
      - weight based wild card concentration:
        - soft min: 3.9 mg/kg
        - hard max: 8.1 mg/kg
      - non weight based, 800 mg/100 mL:
        - soft min: 161 mg
        - hard max: 801 mg
    - added to pediatric library with 2 options, same as above but weight based wild card hard max is 12.1 mg/kg
    - durations for all libraries and options:
      - initial: 1:00
      - soft max: 4:00
      - hard min: 0:55
  ### ustekinumab:
    - add to outpt infusion library
    - 260 mg/250 mL, 390 mg/250 mL, 520 mg/250 mL
    - initial 1:00
    - soft max 3:00
    - hard min 0:55
    - Advisory: This medication must be infused using a 0.2- micron, low protein binding filter.
    - primary only
  ### vancomycin:
    - reviewed outpt infusion and adult libraries, only change is standardizing all mg and g options to same times
  ### vedolizumab:
    - reviewed outpt infusion library
    - added advisory: Following infusion, flush with 30 mL of sterile normal saline or lactated ringers.
  ### zoledronic acid:
    - reviewed adult and outpt infusion library
    - initial duration changed from 0:30 to 0:15
    - add 5 mg/100 mL premixed bag concentration
    - set volume in Cerner inpatient formulary manager to never include in total volume calculation, as there's premixed bags but if unavailable and 5 mg mixed in 100 mL bag then total volume is 106.25 mL and guardrails only allows expressing total volume to the tenth decimal place
    - 4 mg/100 mL, 5 mg/100 mL, and x mg/x mL wildcard concentrations (note volume from drug not needed to be accounted for as Cerner's item in the formulary for the vial is set to not include in total volume calculation)

## 60is 12/23/23:
  ### dalbavancin:
    - add to adult library with mg and gm dosing options
    - mg: 375 mg / 250 mL, 500 mg / 250 mL, 750 mg / 250 mL, 1000 mg / 250 mL, 1125 mg / 250 mL, 1500 mg / 250 mL
    - gm: 0.375 g / 250 mL, 0.5 g / 250 mL, 0.75 g / 250 mL, 1 g / 250 mL, 1.125 g / 250 mL, 1500 g / 250 mL
    - hard min: 25 min
    - soft max: 4 hr
    - initial default: 30 min
    - clinical advisory: If a common IV line is being used to administer other drugs in addition to this drug, the line should be flushed before and after each infusion with D5W.
    - no wildcard option as these cover any indicated doses and dosing adjustments for renal function

## 59is 11/22/23:
  ### insulin:
    - non-weight based:
      - change soft max from 22.5 units/hr to 20 units/hr per protocol
    - weight based:
      - change soft max from 5 units/kg/hr to 0.3 units/kg/hr
      - currently unset hard max, will set to 0.8 units/kg/hr
      - add to pediatric profile

## 58is 09/02/23:
  ### nicardipine:
    - add 50 mg/250 mL double concentrated strength for future scenarios where 40 mg/200 mL premix is out of stock

## 57is 08/16/23:
  ### oxytocin:
    - remove all strengths/therapies except for 30 units/500 mL

## 56is 06/05/23:
  ## updated to current protocol:
  ### esmolol:
      - minor changes to default initial rate/boluses to match protocol
        - 50 mcg/kg/min initial default rate
        - initial default bolus dose removed and made blank as initial boluses can be 250-500 mcg/kg (previously only 250 mcg/kg) and followup boluses are now 250 mcg/kg (changed from 200 mcg/kg)
  ### epinephrine:
      - soft max rate increased from 20 mcg/min to 40 mcg/min
  ### norepinephrine:
      - soft max rate increased from 40 mcg/min to 80 mcg/min
  ### phenylephrine:
      - initial default rate decreased from 100 mcg/min to 20 mcg/min
      - soft max rate increased from 300 mcg/min to 400 mcg/min
  ### dopamine:
      - remove initial default rate (was 2 mcg/kg/min) (titratable and nontritable have different starting rates)
      - no renal dosing protocol listed as an option anymore, remove?
  ### dobutamine:
      - remove intial default rate (was 2 mcg/kg/min) (titratable and nontritable have different starting rates)

  ### zz code only drugs:
      - update all to match regular gaurdrails limits

  ## other changes based on alerts reports:
  ### ceftolazone/tazobactam:
        - soft max duration for all strengths increased from 1:30 to 4:00
        - 3g and 3000mg doses given default durations of 3:00, soft max changed to 6:00
  ### levetiracetam:
        - soft max dose increased from 1500 mg to 2001 mg
        - soft max concentration increased from 15 to 20.1
  ### thiamine:
        - concentration soft max increased from 5 to 10.1

## 55is 04/28/23:
  ### midazolam:
    - add therapy for anti-convulsant
      - 100 mg/100 mL and 250 mg/250 mL
      - initial rate: 0.1 mg/kg/hr
      - soft min: 0.0001 mg/kg/hr  (basically zero)
      - soft max: 2 mg/kg/hr
      - bolus:
        - initial value: 0.2 mg/kg
        - soft min: 0.0001 mg/kg (basically zero)
        - soft max: 0.21 mg/kg
        - rate limits:
          - initial value: 2 mg/min
          - soft min: 1.9 mg/min
          - soft max: 2.1 mg/min

## 54is 04/12/23:
  ### promethazine:
    - concentration limit changed:
      - hard min was 0.123 mg/mL, now 0.031 mg/mL to accommodate doses like 3.125 mg put into a 50 mL or 100 mL bag

## 53is 03/27/23:
  ### promethazine:
    - concentration limits changed:
      - hard min now 0.123 mg/mL (was 1 mg/mL)  (6.25 mg/50.25 mL = 0.124 mg/mL)  (25 mg/51 mL = 0.4902 mg/mL)
      - soft min removed
      - soft max now 1 mg/mL (was 25 mg/ml)

  ### iron sucrose:
    - remove wildcard x mg/x mL concentration from adult library
    - add 100 mg/105 mL, 300 mg/265 mL, and 400 mg/270 mL to adult library (200 mg/110 mL and 500 mg/275 mL already present)
    - dose limits:
      - soft min 99 mg  (was 25 mg)
      - hard max 510 mg
    - 100 mg and 200 mg given same duration limits, 
      - hard min 00:14
      - soft max 08:00
      - initial  00:30
    - 300 mg duration limits
      - hard min 01:25
      - soft max 08:00
      - initial  01:30
    - 400 mg duration limits
      - hard min 02:25
      - soft max 08:00
      - initial  02:30
    - 500 mg duration limits unchanged but for reference
      - hard min 03:25
      - soft max 08:00
      - initial  04:00
    - added 100 mg, 200 mg, 300 mg, 400 mg, and 500 mg to outpt infusion center profile per request

  ### dalbavancin:
    - add to master drug list
    - add wildcard concentrations to outpatient infusion center per request:
      - x mg/x mL 
      - x g/x mL
        - initial duration 00:30
        - concentration limits:
          - soft min 1 mg/mL
          - soft max 5 mg/mL
          - for gram limits 0.001 g/mL and 0.005 g/mL matching the same soft min and soft max for mg

  ### tocilizumab:
    - lower soft min for non weight based to 160 mg (40 kg * 4 mg/kg), previous soft min was 200 mg (weight based already went down to 3.9 mg/kg, but non weight based can now go that low)
    - outpatient infusion center requested Actemra in their library, has been available in their library as tocilizumab since 03/29/22

  ### amikacin:
    - soft max increased from 10 mg/kg to 21 mg/kg
    - hard max added for 31 mg/kg
    - soft min remains at 1 mg/kg
    - concentration limits changed:
      - hard min now 0.2 mg/mL   (was 2 mg/mL)
      - soft min removed
      - soft max now 5.1 mg/mL      (was 11 mg/mL)
    - added to outpatient infusion center profile per request

  ### belimumab:
    - added to master drug list
    - added wildcard concentration as only weight based (not dosed any other way) to outpatient infusion center library per request:
      - x mg/x mL
      - primary only (dedicated iv line required)
      - dose limits:    (only dose for IV is 10 mg/kg, not adjusted for any reasons)
        - soft min 9 mg/kg
        - hard max 11 mg/kg
      - concentration limits: (patients <= 40 kg dilute in 100 mL, > 40 kg dilute in 250 mL)
        - hard min 1.6 mg/mL    (40.1 kg patient * 10 mg/kg = 401 mg represents lowest strength possible in 250 mL, 401 mg/250 mL = 1.604 mg/mL)
        - soft max 10 mg/mL      (40 kg patient * 10 mg/kg = 400 mg; 400 mg/100 mL = 4 mg/mL aka highest strength in 100 mL; for patient to exceed 10 mg/mL would have to be >250 kg; 2500 mg/250 mL = 10 mg/mL)
      - duration limits:
        - hard min 00:55
        - soft max 08:00  (1 hr infusion but can be slowed for infusion related reactions)
        - initial  01:00

  ### vedolizumab:
    - added to master drug list
    - added 300 mg/250 mL to outpatient infusion center per request:
      - duration limits:
        - hard min 00:28
        - soft max 02:00
        - initial  00:30
      - dose limits:    (only dosed IV as 300 mg, not adjusted for any reasons)
        - soft min 299 mg
        - hard max 301 mg

## 52is 03/27/23:
  ### Ferumoxytol:
    fix concentrations to be 510 mg in 117 mL (old was 510 mg in 100 mL) to factor in vial fluid volume of 17 mL for 510 mg
      same for 0.51 g
    same for 1.02 g in 284 mL (old was 1.02 g in 250 mL) with 34 mL vial volume for 1.02 g
      same for 1020 mg
    add to onc infusion center library and outpt infusion center library

## 51is 03/19/23:
  ### Ferumoxytol:
    removed 50 mL sizes for 510, 1020 mg and 0.51 g and 1.02 g
    remove 100 mL for both 1020 mg and 1.02 g
    add 250 mL for 1020 mg and 1.02 g

## 50is 03/19/23:
  ### Ferumoxytol:
    add 510 and 1020 mg in 50 and 100 mL to adult intermittent library
    add 0.51 and 1.02 g in 50 and 100 mL too

## 49is 02/17/23:
  ### insulin drip:
      add weight based dosing per protocol
      non weight based needs removed? probably not will check

## 48is 02/17/23:
  ### epinephrine standard continuous:
      remove hard max of 30 mcg/min, soft max still in place at 20 mcg/min

## 47is 01/30/23:
  ### naloxone drip changes:
    remove 2 mg/500 mL concentration
    add 4 mg/100 mL concentration as sole strength/volume option
      no change to rate limits:
        0.25 mg/hr soft min
        2 mg/hr soft max
        no hard max
        no pre-programmed initial rate
        no bolus
  ### bumetanide continuous:
    - remove wildcard concentration
    - add 24 mg/96 mL as sole strength/volume option
    - no change to rate limits:
      - 0.1 mg/hr soft min
      - 2 mg/hr soft max
      - no hard max
      - 0.5 mg/hr pre-programmed initial rate
      - bolus options:
        - 0.25 mg soft min
        - 4 mg soft max
        - 0.25 mg/min soft min bolus rate
        - 0.5 mg/min hard max bolus rate
        - Lexi: Undiluted direct IV injections may be administered at a rate of 0.5 to 1 mg over 1 to 2 minutes.

## 46is xx/xx/xx (never activated for live pumps):
  ### furosemide drip changes:
    remove 300 mg/30 mL concentration
    remove --- mg/-- mL wildcard concentration
    add 200 mg/100 mL concentration
  ### change soft min for bolus propofol ANES from 19 mg to 10 mg based on number of alerts overridden in anesthesia
  ### updated all protocols if new revisions were found:
    ### heparin drip:
      - change soft min bolus to 24 unit/kg (was 30) for newest protocol only for standard/peripheral vascular disease and VTE, cerebrovascular has no bolus
      - change soft max bolus for standard to 62 unit/kg (was 82, max on protocol is 60
      - change initial infusion for cerebrovascular to 10 unit/kg/hr (was 15)
    ### increase soft max of nitroglycerin drip from 150 mg/min to 200 mg/min
    ### remove soft max for nitroprusside (3 mcg/kg/min), hard max of 10 mcg/kg/min unchanged

## 45is 01/02/23:
### change epoprostenol for inhalation protocol for syringe pump

## 44is 12/11/22:
### increase soft max of furosemide drip from 10 mg/hr to 40 mg/hr

## 43is 10/28/22:
### change dosing in penG syringe with advisory that 1 unit in pump = 1,000 units on label

## 42is 10/28/22:
  ### add penG to nursery syringe pump library

## 41is 10/14/22:
  ### caffeine & sodium benzoate: add 500mg/1000ml preset for OB with default initial admin times

## 40is 9/16/22:
  ### norepinephrine: 
    - increase soft max from 45 to 60 mcg/min to reflect latest form/policy
  ### phenylephrine/phenylephrine ANES: 
    - lower soft min from 10 and 40 (anes) to 5 mcg/min to allow titrating down
  ### ampicillin: 
    - hard max added as reports showed people programming unasyn doses in, soft max 2.1g hard 2.4g; wildcard concentration remove as well
  ### cefazolin: 
    - soft max increased from 2.3 to 3.1g, standard concentration of 3g/100mL and 3000mg/100mL added; wildcard concentration removed
  ### meropenem: 
    - increased soft max duration from 1h to 3h 10m; remove wildcard concentration
  ### fluids: 
    - raised soft max rates for blood and prbcs from 150 to 301 since they're regular ramped up after initial slower rate is tolerated; raised soft max for FFP from 150 to 201 for the same reasons
  ### pantoprazole: 
    - change pantoprazole ivpb to pantoprazole bolus and pantoprazole gtt to pantoprazole drip, add hard max to drip since that runs at constant rate

## 39is 8/15/22:
  ### change max peds nicardipine bolus from 2000 mcg/kg to 50 mcg/kg.  basing this upon max peds weight being 40 kg

## 38is 8/15/22:
  ### add nicardipine to pediatrics library, all dosing in mcg/kg/min with bolus.
    - based on lexicomp dosing:
      - Dosing: Pediatric
      - Hypertension: Note: Use should be reserved for acute severe hypertension: Limited data available: Infants, Children, and Adolescents: Continuous IV infusion: Bolus dose (optional): Initial: 30 mcg/kg, maximum dose: 2 mg/dose; followed by continuous infusion: Initial: 0.5 to 1 mcg/kg/minute; titrate dose according to blood pressure; rate of infusion may be increased every 15 to 30 minutes; maximum dose: 4 to 5 mcg/kg/minute (AAP [Flynn 2017]; Flynn 2000; Flynn 2001). In a retrospective analysis (n=29; mean age: 7.8 ± 6 years [range: 2 days to 17.9 years]), the mean initial dose was 0.8 ± 0.3 mcg/kg/minute (range: 0.2 to 1.3 mcg/kg/minute), the mean effective dose was 1.8 ± 1 mcg/kg/minute (range: 0.3 to 4 mcg/kg/minute); blood pressure was controlled within 2.7 ± 2.1 hours (range: 0.5 to 9 hours) after starting nicardipine continuous infusion (Flynn 2001).

## 37is 8/01/22:
  ### add zz code drugs to peds library (not done in activated set, changes in 37is for review)
  ### add adenosine double concentrated drip and therapy for pt above 115 kg for FFR in cath lab
  ### change some soft min stops and catches for IV potassium

## 36is 6/26/22:
  ### change mvi from a fluid to an intermittent
  ### add propofol to peds
  ### make seperate therapies for std and dbl conc nitroglycerin

## 35is 5/09/22:
  ### add Bezlotoxumab to infusion center

## 34is 4/28/22:
  # add Teprotumumab and Ocrelizumab to infusion center

## 33is:
  # fix data set and file names to remove non-alphanumeric characters

## 32is 3/29/22:
  # split infusion center profile into onc and outpt, onc left the same, outpt profile removed drugs they requested and added drugs they requested

## 31is 3/28/22:
  # add missing vanc premix concentrations

## 30is 3/28/22:
  # add ob epidural w/ and w/o fentanyl

## 29is 3/17/22:
  # add 50 mg/250 ml nitro

## 28is 3/3/22:
  # update module settings with basic infusion warning enabled, approved and released v28 and enumerated v29

## 27is 3/2/22:
  # mg and mcg fixes for pancuronium and dobutamine. v27 convert to new guardrails editor version
  # add abatacept and golimumab

## 26is 2/16/22:
  # fix hard mins for pancuronium and dobutamine echo stress being below allowed lower limits

## 25is 2/14/22:
  # add fentanyl and versed to continuous due to cadd casette backorders

## 24is 2/2/22:
	added any required missing hard min conc. limits for server upgrade
	DOBUTamine / Echo Stress Test / Weight based
	ketamine ANES / Weight based
	pancuronium / Weight based
	phenylephrine ANES / Non-weight based
	remifentanil ANES / Weight based
	rocuronium ANES / Weight based
	SUFentanil ANES / Weight based
	vecuronium / Weight based

	Peditatrics
	alprostadil / Weight based

## 23is 1/23/22:
	add 25 g/125 mL fat emulsion and extend soft max for fats from 13 to 24 hr
	add sotrovimab catalog code
	add Libary.txt which is just plain text formatted report from Guardrails to more easily track changes to library between commits

## 22is 12/8/21:
	add robaxin IV

## 21is 11/28/21:
	add glucagon drip
	
## 20is 11/25/21:
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

## 19is 8/3/21:
	added phenobarbital
	add new premix vancomycin concentrations
	double check phenobarbital
	add injectafer weight based
	add bamlaniviab/estesivimab entries for all volumes

	check injectafer catalog code interop (done, no change)
	add tocilizumab

	**to do
	
	add leveteracetam gram option?
	add bam/este mapping
	add anticonvulsant protocol
	add valproate grams?

## 18is 7/7/21:
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

## 16i 11/15/20:
	add adenosine drip for cath lab
	add bamlanivimab in preparation for EUA

## 15i 10/12/20:
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

## 14i 6/22/20:
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

## 13i 3/31/20:
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

## 10 & 10i 10/18/18,
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

## 8 5/3/18, Bolus feature removed from diltiazem drips
	changes to occlusion configurations under Pump Module Configuration
	Changed naming for pantoprazole, from 'pantoprazole' to 'pantoprazole gtt' avoid confusion
	Auto-Restart Attempts changed in configuration for Adults and Peds library from 5-->>9
	IVF + oxytocin removed
	'Folic Acid' capitalizations were removed so the entry is just 'folic acid' to be more in line with other entries
	MVI (only vitamins) and MVI(folate+thiamine) added as intermittent options
	Removing IVF + Vitamins from Fluids
	Oxytocin conversion chart made for OB for mL to unit in order to easily access for bolus
	Oxytocin min and max bolus values changed to allow boluses from 1 to 30

## 7 4/6/18, Ketamine ANES added, initial 0.1 mg/kg/hr, soft max 0.5 mg/kg/hr, hard max 1 mg/kg/hr
		Concentrations of 50mg/50ml and 100mg/100ml added until can be narrowed
	Propofol ANES given bolus range of 19-71 mg, initial 30 mg (3 mL); Bolus is 12 mL/min
	zz Code drugs fixed to match their non-zz counterparts

## 6, Oxytocin blank setup removed, entries added under postparum for 10, 20, 30, 40 units in 1000 ml; GO LIVE DATASET

## 5 3/22/18, Post-"finalized" data set, pre-go live
	Double concentrated therapies added for dopamine, dobutamine, norepinephrine, and vasopressin
	Dobutamine Echo Stress therapy added
	Bug fixes and stability improvements
	Added blank setup for oxytocin postpartum with conc. limits

## 4 3/09/18, Finalized data set with changes from data set analysis
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
