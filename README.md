This project demonstrates how to create a simple web application using Streamlit to predict the species of an Iris flower based on its features.
The application uses a RandomForestClassifier from the sklearn library trained on the Iris dataset.

>>How It Works
1. Load the Dataset:
We load the Iris dataset, which contains features (sepal length, sepal width, petal length, petal width) for three different species of Iris flowers.

2. Train the Model:
A RandomForestClassifier is trained on the Iris dataset. This model learns to predict the species of an Iris flower based on the features provided.

3. User Input:
The app provides sliders in the sidebar for the user to input the four features of an Iris flower.
The user can adjust these sliders to set the values of sepal length, sepal width, petal length, and petal width.
4. Make Predictions:
Based on the user input, the model predicts the species of the Iris flower.
The app displays the predicted species and the probability of the prediction.

>>>Code Explanation
1. Loading the Dataset:
iris = load_iris()
X = iris.data
y = iris.target

2. Training the Model:
clf = RandomForestClassifier()
clf.fit(X, y)

3. User Input Features:
Sliders are created in the sidebar for the user to input the features:
sepal_length = st.sidebar.slider('Sepal length (cm)', ...)

4. Display the Input:
The app displays the user input data:
st.subheader('User Input Features')
st.write(df)

5. Make and Display Predictions:
The model predicts the species based on user input:(code)
prediction = clf.predict(df)
st.subheader('Prediction')
st.write(iris.target_names[prediction][0])

The probability of each species is also displayed:
st.subheader('Prediction Probability')
st.write(pd.DataFrame(prediction_proba, columns=iris.target_names))

>>>Running the App
To run the application, make sure you have Streamlit installed. Then, execute the following command in your terminal:
streamlit run your_script_name.py
Replace your_script_name.py with the name of your Python script file.
