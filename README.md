# Hindi_FakeNews_Detection
Hindi Fake News Detection using BiLSTM
<h1>Why BLSTM </h1>
Hindi like many natural languages is context-dependent. The meaning of a word in a sentence can depend on both preceding and following words.
BiLSTM reads the sequence forward and backward, so it captures:
What came before a word (like LSTM)
AND what comes after a word (reverse LSTM)
Traditional LSTM or RNN models only consider past context, which can miss key negations or relationships.

