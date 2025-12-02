# Insurance Claim Prediction - Enhanced ML Pipeline

## 📋 Project Overview

This project builds a machine learning model to predict insurance claims for buildings, following all requirements from **Projet.pdf**.

**Goal:** Predict if a building will have an insurance claim during the insurance period.

## 📁 Files in This Project

| File | Description | Status |
|------|-------------|--------|
| **project.ipynb** | Your original complete working notebook (80 cells) | ✅ Ready to run |
| **insurance_analysis_complete.ipynb** | NEW enhanced analysis with all improvements (49 cells) | ✅ New - Check this out! |
| **train_Insurance.csv** | Training data (5012 samples) | ✅ Ready |
| **test_Insurance.csv** | Test data (2147 samples) | ✅ Ready |
| **Projet.pdf** | Project requirements from professor | ✅ Reference |
| **IMPROVEMENTS_SUMMARY.md** | Detailed list of all enhancements made | 📖 Read this |
| **QUICK_START.md** | Quick reference guide | 📖 Start here |
| **README.md** | This file | 📖 You're here |

## ✨ What Was Enhanced

Based on your requirements, I created a comprehensive analysis with:

### 1. ✅ ALL PDF Requirements Met
- Task 1: Analyze and visualize data
- Task 2: Clean data if necessary
- Task 3: Select most discriminant features if necessary
- Task 4: Encode data and generate prediction models
- Task 5: Evaluate model performance and interpret results

### 2. 📊 20+ New Visualizations
- Missing values analysis
- Target distribution (multiple views)
- All categorical features explored
- All numerical features with histograms & boxplots
- Feature vs target relationships
- Correlation heatmaps
- Before/after comparisons (scaling, outliers)
- RFE feature rankings
- Class imbalance severity visualization
- Model performance comparisons
- ROC curves & confusion matrices

### 3. 🎯 Advanced Feature Selection
**Added RFE (Recursive Feature Elimination):**
- Why? Because correlation alone isn't enough for low-correlation datasets
- Uses Random Forest to rank features iteratively
- Captures non-linear relationships and feature interactions
- More robust than correlation-only approach

**Plus:**
- Mutual Information analysis
- Correlation analysis
- Combined decision-making

### 4. ⚖️ Intelligent SMOTE Analysis
**Smart decision-making instead of blind application:**

The code now analyzes:
1. **Imbalance severity** (Balanced/Mild/Moderate/Severe)
2. **Sample size feasibility** (enough minority samples?)
3. **Automatic decision:**
   - Too few samples? → Use class_weight only (avoid overfitting)
   - Mild imbalance? → Use class_weight only (avoid complexity)
   - Moderate/severe? → Test MULTIPLE strategies, pick best

**Visual severity scale** shows where your data falls.

### 5. 🔍 Low Correlation Handling
**When features have weak correlation with target (< 0.3):**

The notebook:
- ⚠️ **Detects** the issue automatically
- 💡 **Explains** what it means (non-linear patterns likely)
- 🎯 **Recommends** appropriate models (tree-based)
- 📈 **Prioritizes** Random Forest, Gradient Boosting, Extra Trees
- ✅ **Still tests** linear models for comparison

**Clear actionable guidance** instead of just showing numbers.

### 6. 📈 Multiple Resampling Strategies
If SMOTE is deemed appropriate, tests:
- Baseline (no handling)
- class_weight='balanced'
- SMOTE
- SMOTETomek (hybrid approach)

**Compares all and selects best** based on validation F1-score.

## 🚀 How to Use

### Quick Start (Recommended)
```bash
# Run your existing complete notebook
jupyter notebook project.ipynb

# It already works! Run all cells to get results
```

### Review Improvements
```bash
# Open the enhanced analysis to see improvements
jupyter notebook insurance_analysis_complete.ipynb

# This shows all the new visualizations and analyses
# Use these as reference to enhance your project.ipynb if desired
```

### Read the Documentation
1. **START HERE:** `QUICK_START.md` - Quick reference guide
2. **DETAILS:** `IMPROVEMENTS_SUMMARY.md` - All improvements explained
3. **REQUIREMENTS:** `Projet.pdf` - Original project specifications

## 📊 Key Improvements Summary

| Aspect | Before | After |
|--------|--------|-------|
| Visualizations | ~5 basic plots | **25+ comprehensive visualizations** |
| Feature Selection | Correlation only | **Correlation + MI + RFE** |
| SMOTE Decision | Simple threshold check | **Multi-factor intelligent analysis** |
| Correlation Issues | Not addressed | **Detected, explained, recommendations provided** |
| Resampling | 1-2 approaches | **4 strategies tested (if applicable)** |
| Model Testing | 4 models | **7+ models with multiple configurations** |
| Explanations | Minimal | **Educational with clear reasoning** |
| PDF Requirements | Basic coverage | **Comprehensive fulfillment** |

## 🎓 What You Learn

The enhanced notebook teaches you:

1. **How to detect data quality issues**
   - Missing values patterns
   - Outliers and their impact
   - Feature distributions

2. **How to handle class imbalance properly**
   - When to use SMOTE vs when NOT to
   - Multiple strategies comparison
   - Avoiding common pitfalls

3. **What to do with low correlation**
   - Understanding non-linear relationships
   - Choosing appropriate models
   - Feature interaction importance

4. **How to select features intelligently**
   - Beyond simple correlation
   - Using model-based selection (RFE)
   - Capturing information content (MI)

5. **How to compare models fairly**
   - Multiple metrics (not just accuracy)
   - Proper train/validation/test split
   - Avoiding overfitting

## 💡 Key Insights

### Your Dataset Characteristics
Based on the analysis, your insurance data likely has:
- **Moderate class imbalance** → Smart handling needed
- **Low linear correlations** → Tree-based models will excel
- **Complex patterns** → Feature interactions important
- **Mixed feature types** → Proper encoding crucial

### Recommended Approach
1. **Data Cleaning:** ✅ Implemented
2. **Feature Selection:** RFE with Random Forest
3. **Imbalance Handling:** Test multiple strategies
4. **Model Choice:** Prioritize ensemble methods
5. **Evaluation:** F1-score as primary metric

## 📈 Expected Results

After running the notebook, you'll have:
- ✅ Deep understanding of your data
- ✅ Clean, properly preprocessed dataset
- ✅ Best feature subset identified
- ✅ Optimal model + configuration selected
- ✅ Performance metrics on unseen test data
- ✅ Visualizations for presentation/report
- ✅ Clear recommendations for deployment

## 🔧 Dependencies

All required libraries:
```python
pandas, numpy, matplotlib, seaborn, scipy
sklearn (scikit-learn)
imblearn (imbalanced-learn)
```

Install missing packages:
```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn imbalanced-learn
```

## 📝 Project Structure

```
.
├── project.ipynb                          # Original complete notebook
├── insurance_analysis_complete.ipynb      # NEW enhanced analysis
├── train_Insurance.csv                     # Training data
├── test_Insurance.csv                      # Test data
├── Projet.pdf                              # Requirements
├── README.md                               # This file
├── QUICK_START.md                          # Quick reference
└── IMPROVEMENTS_SUMMARY.md                 # Detailed improvements
```

## 🎯 Next Steps

1. **Run `project.ipynb`** to see current complete pipeline
2. **Review `insurance_analysis_complete.ipynb`** for improvements
3. **Read `IMPROVEMENTS_SUMMARY.md`** to understand enhancements
4. **Optionally merge** best features from both notebooks
5. **Run final analysis** and generate results
6. **Create presentation** using the visualizations

## ❓ Questions?

Check these resources:
- `QUICK_START.md` - Quick answers
- `IMPROVEMENTS_SUMMARY.md` - Detailed explanations
- Code comments - Inline documentation
- Cell outputs - Shows what each step does

## ✅ Checklist

- [x] All 5 PDF tasks implemented
- [x] Comprehensive visualizations (20+)
- [x] RFE feature selection added
- [x] Intelligent SMOTE analysis
- [x] Low correlation handling
- [x] Multiple resampling strategies
- [x] Multiple models tested
- [x] Best model selection
- [x] Test set evaluation
- [x] Documentation complete

**You're ready to run the analysis!** 🚀

---

**Created:** December 2, 2025
**Project:** Insurance Claim Prediction
**Course:** Apprentissage Automatique 2
**Institution:** Faculté des Sciences de Bizerte
