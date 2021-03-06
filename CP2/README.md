# Challenge Problem 2

In this directory, the following files are provided towards the goal of evaluating team submission data against ground truth data for Challenge Problem #2:

### CP2_eval_script.py
This is the Python script that will be used to compare team submission data against ground truth data.

### ground_truth_sample_CP2.json
This file contains the known ground truth data against which team submissions will be compared.  Each line of this file is a JSON formatted dictionary with the following key-value pairs:
##### key: value
id: An integer that gives the value of the id of the entity match

class: An integer that takes values 0 or 1 and indicates if the entity match is a negative (0) or positive (1)

type: A string that takes values "easy", "medium", or "hard" and indicates the difficulty level of determining if the entity match is negative or positive

site_1: The username found on `site_1`

site_2: The username found on `site_2`

### submission_sample_CP2.json
This file contains the data submitted by the team, which is to be compared against the known ground truth data.  Each line of this file is a JSON formatted dictionary with the following key-value pairs:
##### key: value
id: An integer that gives the value of the id of the entity match

score: An number that takes values between 0 and 1 inclusively, and is a measure of the probability that the two entities given are a positive match, with values closer to 1 indicating a higher probability that the entities are a match.

site_1: The username found on `site_1`

site_2: The username found on `site_2`

### output_sample_CP2.pdf
This file provides a sample of expected output of the evaluation script when run on the sample data files provided with the example usage command shown below.

The file contains an image showing the reciever operating characteristic (ROC) curve for the evaluation of the submission data against the ground truth data.  The value of the area under the curve (AUC) is also noted at the top of the figure.

Note that while this sample output file is in PDF format, the output format is variable and is dependent on the tag of the output file name provided in the command to run the evaluation script.  For example, substituting `output_sample_CP2.pdf` for `output_sample_CP2.png` in the example usage command below will produce an output file format of PNG rather than PDF.

### Example Usages

Note that the file names given in the example usage command below (i.e., `ground_truth_sample_CP2.json submission_sample_CP2.json output_sample_CP2.pdf`) are example file names and can be substituted for the appropriate file names.

Also note that the arguments given after the file name of the `output_sample_CP2.pdf` file are *optional* arguments that list the level of match difficulty to be assessed in the evaluation workflow.

Therefore, to run the evaluation of submission data contained in a file named `submission_sample_CP2.json` against ground truth data contained in a file named `ground_truth_sample_CP2.json` and save the output to a new file named `output_sample_CP2.pdf` while *only assessing matches with difficulty level "medium" or "hard"* use:

`python CP2_eval_script.py ground_truth_sample_CP2.json submission_sample_CP2.json output_sample_CP2.pdf medium hard`

Similarly, to run the evaluation of submission data contained in a file named `submission_sample_CP2.json` against ground truth data contained in a file named `ground_truth_sample_CP2.json` and save the output to a new file named `output_sample_CP2.pdf` while *only assessing matches with difficulty level "easy" or "hard"* use :

`python CP2_eval_script.py ground_truth_sample_CP2.json submission_sample_CP2.json output_sample_CP2.pdf easy hard`

Note that if no difficulty levels are provided, all difficulty levels (i.e., "easy", "medium", and "hard") will be assessed by default.
