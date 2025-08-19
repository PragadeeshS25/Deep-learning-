program:



from keras.models import Sequential
from keras.layers import Dense
import numpy as np
X = np.array([[0,0], [0,1], [1,0], [1,1]])
Y = np.array([[0], [1], [1], [0]])
model = Sequential()
model.add(Dense(1, input_dim=2, activation='sigmoid'))  # only one neuron

model.compile(loss='binary_crossentropy', optimizer='adam', metrics=['accuracy'])
model.fit(X, Y, epochs=100, verbose=0)
preds = model.predict(X)
preds_binary = (preds > 0.5).astype(int)
expected = [0, 1, 1, 0]

print("Test Input | Actual Output | Expected Output | Remarks")
for i in range(len(X)):
    actual = preds_binary[i][0]
    exp = expected[i]

    # Remarks based on correctness
    if actual == exp:
        remark = "Correct"
    else:
        remark = "May fail"

    print(f"{X[i]} {actual} {exp} {remark}")

    output:![1000158937](https://github.com/user-attachments/assets/ecc9dfe9-2c3e-493a-aa3f-8ea79148d92e)
