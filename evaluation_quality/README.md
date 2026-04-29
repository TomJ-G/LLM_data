This folder contains scripts used to assess the quality of LLM evaluation tasks.  
I used tasks as defined in HuggingFace FineTasks:  
https://huggingface.co/spaces/HuggingFaceFW/blogpost-fine-tasks  

How to use the notebook:
1) Save all your results csv file to one folder.
2) Check if your task name is in tasks_metadata (cell 2). If not - add it.
3) Check if number_of_choices for evaluation task is task_n_choices (cell 4). If not - add. If evaluation task has varying number of choices, then I would suggest using average.
4) Run the processing of input files with preprocess_eval_data(paths,tasks_metadata)
5) Run compute_finetasks_quality_metrics:  
   -cpt_df: DataFrame with model names, tasks, checkpoint number, and eval scores  
   -how: if "task" - scores will be calculated per evaluation task. If "model" - scores will be calculated per tested language model  
   -nr_how: defines how we calculate non-randomness. 'simple' - only difference between maximal task score and baseline is calculated. 'average_all' - difference between all checkpoints and baseline is calculated and averaged.  
