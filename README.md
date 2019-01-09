# Mod_3_Project

--Model Goal:
  --Medicaid reviews the average price of certain drug ingredients in the US to determine if they breach the federal upper limit (FUL)
  --We want to build a model that will predict whether a given ingredient (or combination of ingredients) will breach the FUL based on:
    --Ingredient Name
    --Associated ingredient(s)
    --Strength of an ingredient(s) (or dosage)
    --Form of medication (i.e. tablet, etc.)
    --Route (i.e. Oral, etc.)
    --package size
  --Our target for this data set will be whether or not the Medicaid has determined that an ingredient is in violation of the 175% average manufacturer price

--Stretch Goal:
  --Look at the model's predictions to identify which ingredients are most likely to be above FUL and determine what they are used for


Data Source:
  -- http://www.nber.org/data/federal-upper-limits/2017/
    --Dataset explainer: https://www.medicaid.gov/medicaid-chip-program-information/by-topics/prescription-drugs/true-up/xxxxxdraft-true-up-methodology.pdf
  -- Explanation of why same ingredients have different forms/strengths:

    -- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3305679/
      -- Justification for using built in strength dosages
        -- Excerpt:
            -- Partly, this may be due to the difficulty in defining a drug entity in text. In the earlier work that involved automatic drug entity identification [6-9], a drug was simply defined by its generic name/active ingredient. Such approximation may be appropriate for those applications but to formally define a drug, other important specifications should be considered. For instance, a drug's dosage form (DF) indicates the physical form in which a drug is produced and dispensed. It is one of the most important specifications of a drug because it affects the way a drug is administrated in a patient. Drugs with the same ingredients but in different dosage forms can have different uses. For example, if timolol comes as ophthalmic solution (eye drops), it is used to treat glaucoma. If timolol comes as an oral tablet, it is used to treat high blood pressure, to improve survival after a heart attack, and to prevent migraine headaches. Furthermore, dosage forms affect drug absorption and drug distribution in the human body. So in order to confirm drug efficacy and optimize drug therapy, drug pharmacokinetic and pharmacodynamic properties should be modeled and experimented across different dosage forms. For example, tacrolimus, a macrolide with potent immunosuppressive effects, can come as oral capsule and injectable solution. Its pharmacokinetic properties were studied across intravenous, oral, and intramuscular dosage forms [10]. Because of the importance of dosage form in drug development and consumption, it is crucial to provide accurate dosage form information in drug-related information resources.
      --Justification for appropriateness of features:
        --Excerpt
          -- Recent studies have focused on extracting both drug names and related attributes such as strength, route, frequency, form, and duration.
      --Side Bar re NLP:
        -- There was no requirement for normalizing mentions to any standardized nomenclature. More recently, several Natural Language Processing (NLP) systems such as MedEx [13] and MTERMS [14] have been developed to automatically normalize identified drugs to concepts in one or multiple terminologies. These research efforts contribute to the field of automated medication reconciliation across the care continuum [15,16]. They successfully applied NLP techniques to summarize and encode the medication data with high performance (F-Measure > 90%). In these systems, mentions of drug dosage form are captured from clinical narratives but not further normalized to a standard controlled vocabulary.

Future Improvements:
  --Classify drugs
    --add drug types to model
      --http://sideeffects.embl.de/download/
    --Classifications
      --https://en.wikipedia.org/wiki/Anatomical_Therapeutic_Chemical_Classification_System

Current Thoughts:
  --MU: Working to find additional information about the drugs in scope
  --JJ: Write functions that pulls data from Medicare website
    --Provide MU with setlist of ingredients
