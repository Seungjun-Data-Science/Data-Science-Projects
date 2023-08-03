Can Large Language Models (LLMs) Replicate Human Counselor Responses?

Over 50% of the global population grapple with mental health illnesses or disorders. Despite earlier endeavors to create Artificial Intelligence (AI)- powered chatbots for the treatment of mental health issues, the algorithms and frameworks employed fell short in replicating the nuanced dimensions of counseling as practiced by human counselors. This project aims to explore the potential of AI and Large Language models in providing counseling support, with the ultimate objective of enhancing the accessibility of counseling services. Hallmarks of good counselors (e.g. lengthier text, high proportions of positivity in the text etc.) are identified via literature review and some of those aspects are used as points of comparison between human counselor responses and AI (in our case, Dolly) generated responses to mental health patient questions using the CounselChat Data.

- explore_clean.ipynb --> reads data_counsel_chat.csv and produces data_counsel_chat_cleaned.csv
- dolly_generate.ipynb --> reads data_counsel_chat_cleaned.csv and c produces data_counsel_chat_with data_counsel_chat_with_dolly_answers.csv
- cosine_similarity.ipynb --> reads data_counsel_chat_with_dolly_answers.csv and produces dolly_answers_similarity_ipynb
- get_sentiment.ipynb --> reads data_counsel_chat_with_dolly_answers.csv and produces dolly_answers_sentiment.csv
- Team_JSJ_FinalProject.pdf --> Write-Up for the project
