1.) In this example, both the BiLSTM and Transformers got the sentence wrong. The BiLSTM Model managed to capture the sentence structure and got it most syntax correct but did not capture 'red'. As seen in the heatmap (fig 1.1) red attends to "en" whcich is unrelated. The tranformer got the colours right and the sentence seems semanticly correct, but the syntax is wrong. The meaning of the sentence of describing the colours of the couch, is captured however it described it as "wearing" the colours. Both manage to coordinate the nouns with the 'and' seen in (fig 1.2) layer 3 head 6 where 'and' attends to both 'rouge' and 'noir'. 

This could be attributed to a lack of dataset information, and BiLSTM limited understanding of attaching adjectives and long range dependencies. Transformers failure could be attributed to its imited understanding of syntax.

![fig 1.1.](bilstm_example1.png)
fig 1.1.

![fig 1.2.](trans_example1.png)
fig 1.2

2.) In this example both models have correctly assigned the gendered determiner to the nouns. The BiLSTM generally self attends in (fig 2.1.) and doesn't capture any long-term dependencies, it does manage to slightly attend girl to "une" showing some gender understanding. The Transformer manages to identify and strongly attend to the gendered relationship of the masculine and feminine nouns this is seen in (fig 2.2) layer 5 head 2 and layer 3 head 6 where both "girl" and "boy" attends to its appropriate detereminer. The transformer has also managed to pick up the subject of the sentence and attends to the adjectives describing the couch as seen in layer 3 head 2 (red attends to couch). Also in layer 4 head 4 'couch' attends to (fr)'are sitting on' show much deeper understanding.

![fig 2.1.](bilstm_example2.png)
fig 2.1.

![fig 2.2.](trans_example2.png)
fig 2.2

4.)

For this example, both the BiLSTM and Transformers got the sentence wrong, but they got it wrong in different ways. The BiLSTM got it wrong due to syntax and sentence structure, producing something that doesn't make a ton of sense in the first place. The Transformer on the other hand got a sentence that made a little more sense, but is still fairly incorrect. This can be attributed to the transformers ability to gain more structural information about the sentence due to multi-headed attention, and better grammatical understanding of the sentence. Ultimately, both get the sentence wrong in terms of the word cotton and the correct participle of the verb loading. 

This could be attributed to a lack of dataset information, and a limited understanding by both models of proper congugations of verbs and vocabulary.

A particularly interesting observation that supports the observation that the Transformer is more gramatically correct is in its heatmap (fig 4.1). In several layers and heads, such as layer 4 head 4, you can see large amounts of attention being attributed to the phrase 'a group of men'. This means that the model may gain higher understanding of this phrase being a collective noun phrase, thus giving it more ability to structure the outputting sentence in terms of overarching structure.

![fig 4.1.](trans_example4.png)
fig 4.1.


5.)

There error here is in the BiLSTM translation of the phrase. The use of the verb 'passent' translates into the present tense passing, so instead of the sentence 'Two men walked in front of a tent.' we get roughly 'Two men pass in front of a tent'.

This error can be attributed to a lack of proper understanding of what tokens should be properly attended to by the BiLSTM. In the heatmap for the BiLSTM (fig 5.1), you can clearly see that passent attends to walk, but does not attend to the ending 'ed'. This means that it fails to capture the tense of the sentence, generating the false token. Transformers do better in keeping track of the tense, due to the multi-headed attention. This allows for the transformer to have a layer of attention dedicated to something like tenses, and congugations.
This can be observed in Layer 2 (fig 5.2)of the transformer heatmaps, where there is usually a strong attention between the ending 'ed' and the token 'walk'. This helps encode the paring of the tense, causing the more correct french past tense word to be chosen.
![fig 5.1.](bilstm_example5.png)
fig 5.1.


![fig 5.2.](trans_example5.png)
fig 5.2

