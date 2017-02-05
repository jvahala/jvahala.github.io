
## Building the Classification Baseline
We do not have an even distribution of aromas across the 129 hops. We can define baselines success levels for each Aroma's classification from the oil data features. For instance, if we guessed a random hop had the Citrus aroma, we would be correct 42.51% of the time. Any additional classification methods should perform better than these baselines defined in the PERCENT column below. 

|      AROMA     | COUNT | PERCENT |
|:--------------:|:-----:|:-------:|
| Citrus         |   54  |  42.51% |
| Herbal         |   48  |  37.80% |
| Spicy          |   48  |  37.80% |
| Floral         |   47  |  37.01% |
| Fruity         |   43  |  33.86% |
| Earthy         |   29  |  22.83% |
| Tropical Fruit |   16  |  12.60% |
| Pine           |   16  |  12.60% |
| Grassy         |   8   |  6.30%  |
| Cedar          |   7   |  5.51%  |
| Stone Fruit    |   6   |  4.72%  |
| Green          |   1   |  0.79%  |



## One vs. All Classifier
First, we will try the simplest, dumbest method where we define new features via a [Gaussian Kernel](https://en.wikipedia.org/wiki/Radial_basis_function_kernel) and use those features to form separating subspaces using [Support Vector Machines](https://en.wikipedia.org/wiki/Support_vector_machine). Because we have many different labels (each aroma is its own set of 0/1 labels), we need to do something more special than basic binary classification. The One vs. All (OVA) approach is this simple, dumb method we will try first. There are more complicated methods like those involving [Error Correcting Codes](https://en.wikipedia.org/wiki/Error_detection_and_correction), but OVA is simple and [tough to beat](http://www.jmlr.org/papers/volume5/rifkin04a/rifkin04a.pdf).  

