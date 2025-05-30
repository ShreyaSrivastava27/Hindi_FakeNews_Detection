# Hindi_FakeNews_Detection
Hindi Fake News Detection using BiLSTM
<h1>Why BLSTM </h1>
Hindi like many natural languages is context-dependent. The meaning of a word in a sentence can depend on both preceding and following words.
BiLSTM reads the sequence forward and backward, so it captures:
What came before a word (like LSTM)
and what comes after a word (reverse LSTM).
Traditional LSTM or RNN models only consider past context, which can miss key negations or relationships.
 <h1>Data Loading & Labeling</h1>
<ul><li>Loads fake_news_basic.csv (label = 0) and true_news_basic.csv (label = 1).</li>

<li>Ensures both datasets have equal size and combines them.</li></ul>

<h1>Text Preprocessing</h1>
<ul>
<li>Cleans and stems Hindi news headlines.</li>
<li>Removes Hindi stopwords using NLTK + custom list.</li>
<li>Converts text into numerical one-hot encoded vectors.</li>
<li>Pads sequences to uniform length (maxlen=20).</li></ul>

<h1>Model Creation (BiLSTM)</h1>
Uses a Bidirectional LSTM model with:
<ul>
<li>Embedding layer (converts words to vectors)</li>
<li>BiLSTM (captures context in both directions)</li>
<li>Dropout + Dense layers</li>
<li>Binary classification output (sigmoid).</li></ul>

<h1>Model Training</h1>
<ul>
<li>Splits data (70% train, 30% test).</li>
<li>Trains model for 10 epochs using binary_crossentropy loss and adam optimizer.</li></ul>

<h1>Prediction & Flask Integration</h1>
<ul>
<li>Starts a Flask web server.</li>
On form submit (/prediction route):
<li>Preprocesses input text like training data.</li>
<li>Predicts whether the headline is real (True) or fake (False).</li>
<li>Renders result in prediction.html.</li></ul>



