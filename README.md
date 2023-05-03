Download Link: https://assignmentchef.com/product/solved-cs1675-homework8-decision-stumps
<br>
In this exercise, you will implement a decision stump (a very basic classifier) and a boosting algorithm. You will also complete an exercise to help review basic probability, in preparation for discussing probabilistic graphical models.

<u>Part I: Decision stumps</u>

Implement a set of decision stumps in a function <span style="font-family: courier new;">decision_stump_set</span>.

<b>Instructions:</b>

<ul>

 <li>[5 pts] Each decision stump operates on a single feature dimension and uses a threshold over that feature dimension to make positive/negative predictions. This function should iterate over all feature dimensions, and consider 10 approximately equally spaced thresholds for each feature.</li>

 <li>[3 pts] If the feature value for that dimension of some sample is over/under that threshold (using “over” defines one classifier, and using “under” defines another), we classify it as positive (+1), otherwise as negative (-1).</li>

 <li>[5 pts] After iterating over all combinations, the function should pick the best among these Dx10<span style="color: red;">x2</span> classifiers, i.e. the classifier with highest weighted accuracy <span style="color: red;">(i.e. lowest weighted error)</span>.</li>

 <li>[2 pts] Finally, for simplicity, rather than defining a separate function, we will use this one to output the label on the test samples, using the best combination of feature dimension, threshold, and over/under.</li>

</ul>

<b>Inputs:</b>

<ul>

 <li>an NxD matrix <span style="font-family: courier new;">X_train</span> (N training samples, D features),</li>

 <li>an Nx1 vector <span style="font-family: courier new;">y_train</span> of ground-truth labels for the training set,</li>

 <li>an Nx1 vector <span style="font-family: courier new;">w_train</span> containing the weights for the N training samples, and</li>

 <li>an MxD matrix <span style="font-family: courier new;">X_test</span> (M test samples, D features).</li>

</ul>

<b>Outputs:</b>

<ul>

 <li>an Nx1 binary vector <span style="font-family: courier new;">correct_train</span> containing 1 for training samples that are correctly classified by the best decision stump, and 0 for incorrectly classified training samples, and</li>

 <li>an Mx1 vector <span style="font-family: courier new;">y_pred</span> containing the label predictions on the test set.</li>

</ul>

<u>Part II: AdaBoost</u>

In a function <span style="font-family: courier new;">adaboost</span>, implement the AdaBoost method defined on pages 658-659 in Bishop (Section 14.3). Use decision stumps as your weak classifiers. If some classifier produces an α value less than 0, set the latter to 0 (which effectively discards this classifier) and exit the iteration loop.

<b>Instructions:</b>

<ol>

 <li>[3 pts] Initialize all weights to 1/N. Then iterate:</li>

 <li>[7 pts] Find the best decision stump, and evaluate the quantities ε and α.</li>

 <li>[7 pts] Recompute and normalize the weights.</li>

 <li>[3 pts] Compute the final labels on the test set, using all classifiers (one per iteration).</li>

</ol>

<b>Inputs:</b>

<ul>

 <li><span style="font-family: courier new;">X_train</span>, <span style="font-family: courier new;">y_train</span>, <span style="font-family: courier new;">X_test</span>, and</li>

 <li>a scalar <span style="font-family: courier new;">iters</span> defining how many iterations of AdaBoost to run (denoted as M in Bishop).</li>

</ul>

<b>Outputs:</b>

<ul>

 <li>an <span style="color: red; font-family: courier new;">M</span>x1 vector <span style="font-family: courier new;">y_pred_final</span>, containing the final labels on the test set, using all <span style="font-family: courier new;">iters</span> classifiers.</li>

</ul>

<u>Part III: Testing boosting on Pima Indians</u> (10 pts)

In a script <span style="font-family: courier new;">adaboost_demo.m</span>, test the performance of your AdaBoost method on the Pima Indians dataset. Use the train/test split code (10-fold cross-validation) from HW<span style="color: red;">4</span>. Convert all 0 labels to -1. Try employing (10, 20, 50) iterations. Compute and report (in <span style="font-family: courier new;">report.pdf/docx</span>) the accuracy on the test set, using the final test set labels computed above.

<u>Part IV: Probability review</u> (5 points)

In your report file, complete Bishop Exercise 1.3. Show your work.

<b>Submission:</b> Please include the following files:

<ul>

 <li><span style="font-family: courier new;">decision_stump_set.m</span></li>

 <li><span style="font-family: courier new;">adaboost.m</span></li>

 <li><span style="font-family: courier new;">adaboost_demo.m</span></li>

 <li><span style="font-family: courier new;">report.pdf/docx</span></li>

</ul>