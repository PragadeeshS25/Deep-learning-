program 


import numpy as np
test_indices = [7, 3, 8, 1]   # <-- these are labels we want to check
samples = []
for label in test_indices:
    idx = np.where(y_test == label)[0][0]  # first occurrence
    samples.append(idx)

for idx in samples:
    img = X_test[idx].reshape(1, 28, 28, 1)  # reshape for model input
    expected = y_test[idx]
    pred = np.argmax(model.predict(img, verbose=0))
    correct = "Y" if expected == pred else "N"
    print(f"Image of {expected}: Expected Label is {expected}, Model Output is {pred}, Correct (Y/N) is {correct}")


    output:![1000158925](https://github.com/user-attachments/assets/6b2d6a72-d9c2-4149-8b6a-9f550630e908)
