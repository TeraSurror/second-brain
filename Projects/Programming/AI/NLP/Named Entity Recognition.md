### LSTMs
Read this blog for details: https://colah.github.io/posts/2015-08-Understanding-LSTMs/

### NER: Named Entity Recognition
- locates and extracts predefined entiites from text

Examples:
Sharon flew to Miami last Friday
Sharon -> person
Miami -> geographic entity
Friday -> time  

Training an NER system:

1. Create a tensor for each input and its corresponding number
2. Put them in a batch
3. Feed it to an LSTM unit
4. Run the output through a dense layer
5. Predict using a log softmax over K classes
