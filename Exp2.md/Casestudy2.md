program:


import numpy as np
class_names = ['T-shirt', 'Trouser', 'Pullover', 'Dress', 'Coat',
               'Sandal', 'Shirt', 'Sneaker', 'Bag', 'Ankle boot']
sample_indices = [0, 1, 2, 3]   

print("\nSample Predictions:\n")
print("{:<12} {:<12} {:<15} {:<10}".format("Input Image", "True Label", "Predicted Label", "Correct (Y/N)"))

correct_count = 0

for i, idx in enumerate(sample_indices):
    img = X_test[idx].reshape(1, 28, 28, 1)
    true_label = y_test[idx]
    pred_label = np.argmax(model.predict(img, verbose=0))

    true_name = class_names[true_label]
    pred_name = class_names[pred_label]

    correct = "Y" if true_label == pred_label else "N"
    if correct == "Y":
        correct_count += 1

    print("{:<12} {:<12} {:<15} {:<10}".format(true_name, true_name, pred_name, correct))

sample_acc = correct_count / len(sample_indices) * 100
print(f"\nSample Accuracy: {sample_acc:.2f}%")

output:![1000158927](https://github.com/user-attachments/assets/f7fc8eaa-b8aa-40ff-8254-2a11c67d158d)
