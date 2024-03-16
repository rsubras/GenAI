## FunctionDef eval_rouges(refrence_summary, model_summary)
**eval_rouges**: The function of eval_rouges is to calculate ROUGE (Recall-Oriented Understudy for Gisting Evaluation) and BLEU (Bilingual Evaluation Understudy) scores for a reference summary and a model summary.

**parameters**:
- refrence_summary: A string representing the reference summary.
- model_summary: A string representing the model summary.

**Code Description**:
The eval_rouges function utilizes the RougeCalculator class to calculate ROUGE-1, ROUGE-2, ROUGE-L, and ROUGE-BE scores, as well as the BLEU score using the BLEUCalculator class. It takes the reference summary and model summary as input, computes the respective scores, and returns them as a tuple containing ROUGE-1, ROUGE-2, ROUGE-L, ROUGE-BE, and BLEU scores.

**Note**:
- The function requires the RougeCalculator and BLEUCalculator classes for ROUGE and BLEU score calculations.
- Ensure that the input reference and model summaries are provided in the correct format for accurate evaluation.

**Output Example**:
(0.75, 0.55, 0.65, 0.45, 0.80)
