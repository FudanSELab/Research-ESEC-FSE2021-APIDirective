# Replication Package of Learning Based Extraction Of First-Order Logic Representations of API Directives

## Empirical Study

- Keywords for sampleing candidate sentence
> call*, invo*, before, after, between, once, prior, generic, must, mandat*, require*, shall, should, encourage*, recommend*, may, restrictions assum*, only, debug*, restrict*, never, condition*, strict*, necessar*, portab*, strong*, performance, performan*, efficien*, fast, quick, better, best, concurrency, concurren*, synchron*, lock*, thread*, simultaneous*, alternative, desir*, alternativ*, addition*, subclassing, extend*, overrid*, overload*, overwrit*, reimplement*, subclass*, super*, inherit*, warning, warn*, aware*, error*, note*, equal, equivalent, less, fewer, greater, larger, smaller, below, same, range, outside, negative, positive, nonnegative, nonpositive, null, nullable, non-null, <, >, >=, <=, =, !=, instance of, derived from, between, one of

- [1167 Candidate Sentence](https://github.com/APIDirective/APIDirective.github.io/blob/master/empirical_research/1167_Candidate_Sentences.xlsx). We sample 1167 candidate sentences from the reference documentation of JDK 1.81 that include one of the keywords or conform to one of the regular expressions based on two criteria: sample at least 200 sentences from each of the five types of text; sample at least 5 sentences for each keyword or regular expression. 

- [Directive sentences annotation for candidate sentences](https://github.com/APIDirective/APIDirective.github.io/blob/master/empirical_research/directive_sentences_annotation_for_candidate_sentences.xlsx). Two of the authors independently examine the sampled sentences to annotate whether they express API directives or not. For the sentences that are annotated differently, a third author joins and makes the decision. In this excel file, the column “text” represents the sentence, the column "doc_name" represents the API name. And the column "directive_result_by_author_1", "directive_result_by_author_2",  represents two authors annotated result, the column "arbitration_directive_result" represents the arbitration result, “T” means that sentence is a directive sentence, “F” means not.

- [729 directive sentences with identified FOL fomulas](https://github.com/APIDirective/APIDirective.github.io/blob/master/empirical_research/729_directive_sentences_with_identified_FOL_fomulas.xlsx). Two of the authors annotate the atomic formulas implied in the 729 directive sentences independently. In this excel file, the column "text" represents the sentence, the column "doc_name" represents the API name. And the column "FOL_by_author_1", "FOL_by_author_2", represents two authors annotated result.

## Directive Sentence Classifier
- [Directive sentence classifier training data](https://github.com/APIDirective/APIDirective.github.io/blob/master/fast_text/classifier_train_data.txt). The training data for a directive sentence classifier includes 16292 sentences, which have 8,314 directive sentences and 7,978 non-directive sentences. 

## Atomic Formula Extraction

### manually annotated data for training BERT-BiLSTM-CRF model
- [Manually annotated data for training BERT-BiLSTM-CRF model](https://github.com/APIDirective/APIDirective.github.io/blob/master/entity_recognization/valid.json). The annotation data for entity recognization without negative data. The data is annotated by four master students manually. Each directive sentence is annotated by two annotators independently. If their annotators
are different, one of the authors will join and resolve the conflict using the majority strategy. As a result, we obtained 3226 annotated directive sentences with 7,045 arguments.

### Automatically generated annotated data for training BERT-BiLSTM-CRF model
- [Automatically generated annotated data for training BERT-BiLSTM-CRF model](https://github.com/APIDirective/APIDirective.github.io/blob/master/entity_recognization/train_data.json). The training data for entity recognization extended automatically. Based on the annotated sentences, we use a series of heuristic rules to generate more training data. Finally, we obtain 11,019 annotated directive sentences with 16,972 annotated arguments as the training data.

## Logical Relation Recognition
- [51 linguistic patterns for conditional Structure Parsing](https://github.com/APIDirective/APIDirective.github.io/blob/master/entity_linking/sentence_pattern.xlsx). Conditional structure parsing is done by linguistic pattern matching. We defined 51 linguistic patterns to recognize the logical relations between the extracted atomic formulas. If the sentence matches more than one linguistic patterns, we parse it according to the most complete and concrete pattern, i.e., the pattern that has the most conditional conjunctions and the deepest nested structure.

## Argument Parsing
- [Manually annotate 246 API related arguments for training SVM model](https://github.com/APIDirective/APIDirective.github.io/blob/master/entity_linking/manually_annotate_246_API_related_arguments_for_training_SVM_model.json). The training data is used to train an SVM model for the API linking. To prepare the training data we manually annotate 246 API related arguments from the annotated formulas in the empirical study.

## Code Review Tasks RQ4 
- [CodeReviewTasks](https://github.com/APIDirective/APIDirective.github.io/blob/master/CodeReview/Code%20Review%20Tasks.xlsx).
