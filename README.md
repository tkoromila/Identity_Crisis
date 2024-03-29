# Cell_Reports
Distinct roles of broadly-expressed repressors support  dynamic enhancer action and change in time

Cell Reports, 2019, https://doi.org/10.1016/j.celrep.2019.06.063

Segmentation and Matlab code description:

To start analysis of data for nc11 or later timepoints, MCP-GFP and Nup-RFP slices were maximally projected for each time point using Fiji
software. 
For segmentation of the signal in both channels, we first used a Gaussian Filter (GF) (GF=0.55) in Fiji software as used in other MS2-MCP
Drosophila imaging pipelines (Bothma et al., 2014; Garcia et al., 2013), to both reduce pixel-level noise and to smooth small-scale image
variations within a single object. Next, we developed a Matlab computational pipeline to process images from the two channels (488nm
channel: MCP-GFP, 555nm channel: Nup-RFP) used to collect our data, which consisted of approximately 2 hours of imaging and ~80 scans. 
Specifically: (I) Embryo boundaries were detected in 3D using Nup-RFP filtered images, using customized code. We delineated the embryo
boundary in a semi-automated fashion by manually defining extreme dorsal and ventral points. The boundary coordinates were then propagated
along the MCP-GFP iso-intensity lines using Matlab’s bwboundary function. (II) Nascent dot intensity determination requires an estimate of
the background for each dot for the sog_Distal.MS2 transgene. We used scripts for segmentation of both MCP-GFP and Nup-RFP signals. MCP
GFP labeled transcriptional dots falling outside Nup-RFP labeled nuclei were excluded. To segment the transcriptional dots in a uniform
manner across all datasets, we applied Gaussian Filter (GF) using Fiji Software as well as thresholded the MCP-GFP channel at 30% (i.e.
BTH=0.30) of maximum intensity (e.g. Fig. 3F,H and Fig. S2D, Background Threshold (BTH): grey dotted line). A less stringent threshold
point (BTH=0.25) was tested but rejected (data available for comparison Fig. S3A,B,E) because false positives were obtained for early
timepoint at nc9. Only the 30% threshold (BTH=0.3) eliminates the background from the non-nuclear regions in a conservative manner for all
constructs assayed. BTH=0.35 was explored but resulted in over 40% loss of signal at many timepoints, and therefore was only used for
comparison sake (Fig. S3C,D,F).
Finally, after thresholding and before quantification analysis, the segmentation and tracking was also visually checked frame by frame
over multiple nuclear cycles in order to verify the dot’s location relative to nuclear membranes (Nup-RFP). An analysis of these
measurements for three to six embryos was performed to define the number of total active nuclei and associated standard error of the mean. 
