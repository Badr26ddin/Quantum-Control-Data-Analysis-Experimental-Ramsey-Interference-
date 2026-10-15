# Results and Limitations

## 1. Results

This project investigates experimental motional Ramsey interference data from the open dataset [*Experimental Data — Quantum non-Gaussian coherences of an oscillating atom*](https://zenodo.org/records/15797402). The analysis focuses on the \(|0\rangle + |1\rangle\) superposition state and examines how the estimated Ramsey fringe contrast changes with the waiting time.

The dataset contains excitation probabilities recorded during phase scans of the second Ramsey pulse. The analysis preserves the original measurements and uses a consistent 180-point window for complete scans with a phase step of two.

An empirical phase multiplier of **3.994** was estimated from the experimental scans. Using this working phase model, the fringe contrast was estimated at each delay by fitting a sinusoidal function to the measured excitation probabilities.

For the nine delay settings between 0.1 ms and 40 ms, the estimated contrast showed a general decreasing trend. It ranged from approximately 0.91 at 0.1 ms to 0.56 at 40 ms, with a maximum value of approximately 0.95 at 1 ms. The small non-monotonic variations at short delays were retained rather than manually smoothed.

An exponential decay model was subsequently fitted to these nine contrast estimates:

\[
C(\tau)=C_0\exp(-\tau/T)
\]

The resulting exploratory parameter estimates were:

| Parameter | Estimate |
|---|---:|
| Initial contrast, \(C_0\) | 0.9373 |
| Exponential decay parameter, \(T\) | 74.67 ms |
| Approximate 95% interval for \(T\) | 69.36–79.97 ms |
| Reduced chi-squared | 2.76 |
| Number of delay settings fitted | 9 |

These values describe the exponential model fitted to the selected contrast estimates. The decay parameter is an exploratory result and is not presented as a validated measurement of the system's coherence time.

## 2. Data Quality Assessment

The original Ramsey archive contains 177 Excel files across several motional superposition states. All files were inspected for their structure, missing values, probability bounds and scan lengths.

The primary analysis focused on the \(|0\rangle + |1\rangle\) state. Nine delay settings passed the working selection criteria: a fringe-fit \(R^2\) of at least 0.90 and a delay no greater than 40 ms.

Two long-delay measurements were flagged for review:

- **80 ms:** The file contains 169 measurements, fewer than the 180-point window used for a complete phase scan. Its fitted fringe has poor quality under the current model.
- **120 ms:** A 180-point window is available, but the fitted fringe has an \(R^2\) of approximately 0.49, indicating that the current model does not describe the measured pattern well.

These measurements were retained in the data-quality record but excluded from the primary exponential fit. Their exclusion is based on predefined analysis criteria rather than on their effect on the desired decay result.

## 3. Statistical Interpretation

The estimated decay parameter changed only modestly when individual delay settings were omitted one at a time. This indicates numerical stability under that particular sensitivity test.

However, the reduced chi-squared value of 2.76 suggests that the observed deviations from the exponential curve are larger than would be expected under the current uncertainty estimates and model assumptions. The reported interval should therefore be interpreted as approximate and conditional on the fitting procedure.

The exponential model is used here as a compact description of the observed trend. A good-looking curve, a high \(R^2\), or numerical stability alone does not establish that the model is the correct physical description.

## 4. Limitations

**Phase calibration.** The archived Ramsey files provide excitation probabilities but do not contain an explicit phase value for every measurement. The phase coordinate is reconstructed from the row order and the documented phase-step setting. The multiplier of 3.994 was estimated empirically from the same data rather than confirmed by an independent calibration. Consequently, the derived contrast values remain conditional on this phase-mapping assumption.

**Model uncertainty.** The sinusoidal model does not describe every delay scan equally well, particularly at longer delays. The current analysis does not fully account for uncertainty in the phase model, the choice of oscillation frequency, or alternative physical models.

**Uncertainty estimates.** The contrast uncertainties are approximate regression-based estimates. They do not include every source of experimental uncertainty, such as phase drift, variation between repeated scans, or uncertainty in the underlying measurement statistics.

**Incomplete and poorly fitted scans.** The 80 ms scan is shorter than the expected complete scan window. The 120 ms scan has poor fringe-fit quality under the current model. Both require further investigation before they can support a quantitative conclusion about long-time coherence.

**Limited fitting range.** The primary exponential fit uses nine delay settings between 0.1 ms and 40 ms. The decay parameter is therefore dependent on the selected time range and the exponential model; it should not be extrapolated as a validated physical lifetime.

## 5. Conclusion

The exploratory analysis reveals a clear overall reduction in estimated Ramsey fringe contrast with increasing delay for the selected \(|0\rangle + |1\rangle\) measurements. An exponential curve provides a compact summary of the trend over the selected delay range, with an estimated decay parameter of approximately 74.67 ms.

The main contribution of this analysis is a reproducible workflow for downloading, inspecting, visualizing and fitting open experimental quantum-physics data while documenting data-quality issues and model limitations.

Further work should independently verify the phase mapping, examine the long-delay scans, and test the fitting procedure against the experimental analysis described in the original publication before interpreting the decay parameter as a physical coherence time.

## References

1. Kovalenko, A. et al. *Quantum non-Gaussian coherences of an oscillating atom*. Physical Review Research 7, 033075 (2025). [https://doi.org/10.1103/5nxx-r97j](https://doi.org/10.1103/5nxx-r97j)
2. Kovalenko, A. et al. *Experimental Data — Quantum non-Gaussian coherences of an oscillating atom*. Zenodo (2025). [https://zenodo.org/records/15797402](https://zenodo.org/records/15797402)
3. Kovalenko, A. et al. Supplementary Material, *Quantum non-Gaussian coherences of an oscillating atom*. [APS supplementary material](https://journals.aps.org/prresearch/supplemental/10.1103/5nxx-r97j/QNG_coherence_supplement.pdf)
