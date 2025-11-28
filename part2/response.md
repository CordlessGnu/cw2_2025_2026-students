a.)

| Model                 | Embedding Size | Hidden Size | Dropout | BLEU Score |
| --------------------- | -------------- | ----------- | ------- | ---------- |
| Seq-2-Seq Large       | 128            | 128         | 0.2     | 52.608     |
| --------------------- | -------------- | ----------- | ------- | ---------- |
| Model                 | Embedding Size | Head Size   | Dropout | BLEU Score |
| --------------------- | -------------- | ----------- | ------- | ---------- |
| Transformer Small     | 16             | 8           | 0.1     | 16.878     |
| Transformer Medium    | 64             | 16          | 0.1     | 46.270     |
| Transformer Large     | 192            | 32          | 0.1     | 48.450     |
| Transformer X-Large   | 264            | 22          | 0.1     | 48.970     |

b.)
![alt text](training.png)
![alt text](devLoss.png)

c.)
As demonstrated by the Bleu scores and analyzing the given translations for each of the ablations of the model, the transformer architecture for the downstream task of French translation tends to get better as you increase embedding and hidden size. The returns on enlarging the embedding size decreasse rapidly seen in the jump from large to X-large, for further improvement a large training dataset could be beneficial. Comparing the Highest performing seq2seq model with the transformers shows that both models can perfrom adequately on the task, however it does seem that seq2seq perfroms slightly better overall. When comparing the small transformer and the small seq2seq which had the same embedding size the transformer managed to achieve twice the BLEU score (7 vs 16) hinting that the multi-head attention can achieve better understanding and extract liguistic features. The larger models did not converge and had to be stopped earlier, running further tests with different hyperparameters could show better transformer results.
