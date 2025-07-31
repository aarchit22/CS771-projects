# CS771-Project
This project was done in 2024-2025 odd semester under Prof. Piyush Rai
# Mini Project - 1
In this mini-project, we are provided 3 binary classification datasets. Each of these datasets
represents the same machine learning task (which can be posed as a binary classification problem) and was generated from the same raw datase.
### Dataset Description
* Emoticons as Features Dataset : <br>
The features of each input are given in form of 13 emoticon.<br>
Example : input_emoticons: ":
😥😓😊😘😷😌😠🤡😉👍🚴...", label:"0"

* Deep Features Dataset : <br> The features of each input are extracted using a simple deep neural network. This resulted in each input being represented using a 13 × 786 matrix which basically consists of
786-dimensional embeddings of each of the 13 emoticon
features of an input.<br>
Example: features: [[0.1, -0.3, 0.5, ...], ...] label: "0"

* Text Sequence Dataset :<br> The features of each input are given in form of a length 50 string consisting of 50 digit.<br>
Example: input_str: "0241812141226549266461...", label_str: "0"
### Task-1
The first task was to train some binary classification models on each of the 3 datasets and pick the the best possible binary classification model for each of the 3 dataset.

### Task-2
In the second task we had to investigate if using all 3 training datasets together, we can learn an even better model that has better accuracy than the models learned on each of the 3 individually.

# Mini Project - 2

In this mini-project we were provided 20 training datasets $D_1$, $D_2$, . . . , $D_{20}$, each of which was a subset of the
CIFAR-10 image classification dataset. Out of these 20 datasets, the first 10 datasets $D_1$, $D_2$, . . . , $D_{10}$ have their inputs from the same distribution (which means the input features’ characteristics of datasets $D_1$ to $D_{10}$ are similar to each other, or equivalently we can say that $p(x)$ is the same for all these datasets), whereas $D_{11}$, $D_{12}$, . . . , $D_{20}$ have their inputs from 10 different input distributions (thus $p(x)$ is different for each of these datasets).

The first dataset $D_1$ is labeled and the remaining 19 datasets are unlabeled.

### Task-1
Using $D_1$, train a model $f_1$ using an LwP classifier , and then apply $f_1$ to predict the labels of $D_2$ (note
that its true labels are not known), use $D_2$ along with its predicted labels to update $f_1$ to $f_2$.

Now use $f_2$ to predict the labels of $D_3$ and update $f_2$ to $f_3$ in the same way as we updated $f_1$ to $f_2$. We had to keep doing this for the first 10 datasets $D_1$, $D_2$, . . . , $D_{10}$ and learn 10 models $f_1$, $f_2$, . . . , $f_{10}$.

Apply each model $f_i \in \{ f_1, f_2, \dots, f_{10} \}$ on the $i$-th held-out dataset $\hat{D}_i$ as well as the previous held-out datasets $\hat{D}_j$, where $j < i$.

For example:
- Apply $f_3$ on $\hat{D}_3$, $\hat{D}_1$, and $\hat{D}_2$.

Finally, report the accuracies of each model on each held-out dataset.

### Task-2
Next, starting with $f_{10}$ from task 1 as the initial model, repeat the same procedure using the datasets $D_{11}, D_{12}, \dots, D_{20}$ (again, one dataset at a time) to learn models $f_{11}, f_{12}, \dots, f_{20}$.

Once you have learned $f_{11}, f_{12}, \dots, f_{20}$, apply each model $f_i \in \{ f_{11}, f_{12}, \dots, f_{20} \}$ on the $i$-th held-out dataset $\hat{D}_i$ as well as the previous held-out datasets $\hat{D}_j$, where $j < i$.

For example:
- Apply $f_{13}$ on $\hat{D}_{13}$, $\hat{D}_{1}$, $\hat{D}_{2}$, $\dots$, $\hat{D}_{12}$.

Finally, report the accuracies of each model on each of these held-out datasets.
