Daniel would like to add a new model into the models folder.

Daniel will provide a hugging face link and/or additional URLs, like the vendor website.

The objective is as follows:

The models folder contains anindex of models that meet the scope of the repository: they are audio multimodal Models which allow users to provide audio data accompanied by text prompts and to derive inference (outputs) that "understands" both elements. 

Daniel is primarily interested in these models because of the significant advantages that he sees them as having over traditional STT and ASR. The repository contains context.

Each model should be added as a separate markdown document. The marked in document should contain badges at the top linking to the hugging face model card as well as the vendor website if it has one. 

When drafting the initial model pages in this repository, keep the following in mind:

- The objective is not to mindlessly regurgitate vendor marketing claims. 
- Daniel's vantage point - At the vantage point for which this repository is created - is that of "builders"  
- This community is interested in knowing the details about the model in terms of the training capabilities, inference, availability, etc. 
- Sometimes the model cards on hugging face will contain a level of detail that is actually unhelpful to developers at the implementation level, who are more focused on what the model can actually achieve in real speech to text workflows than internal architecture. 

It is also very interesting to Attempt to Gage the approximate size of the user base how long the model has been available for. Limitations surrounding the type of audio data that it can process, such as the maximum duration of audio. 

As the focus in this repository is identifying open source multimodal models, it's also very useful to know the parameters and quantizations that are available as these are very important in determining whether these models are practicable in self hosted or local environments as well as in production ones. 

Some background details about the company driving for the model and its philosophy is also very relevant. You may be still include for example a background about the company, the team, where it's based on what their history is so far in the audio AI space. 

In addition to creating the link for the model, add it to models/index.md