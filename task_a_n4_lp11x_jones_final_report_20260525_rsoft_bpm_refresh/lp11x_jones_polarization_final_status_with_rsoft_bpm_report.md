# Task A N4 LP11x-like Jones-Polarization Final-Status Report With RSoft/BPM Addendum

日期：2026-05-25
报告类型：当前可行性/阶段性最终结果报告刷新包
对象：`task_a_n4_lp11x_like_camera_two_lobe`

## 本轮刷新结论

本刷新包保留 2026-05-22 Lumerical EME + COMSOL feasibility 结论，并新增 RSoft BeamPROP/BPM 可行性证据。当前候选仍是 `phase-amplitude-polarization` 的 `4 core x/y Jones` 架构；本轮没有重新做全范围几何扫参、eta 优化或 robustness。

新增 RSoft/BPM 结果为真实 `bsimw32` coarse/refined 执行加本地 scalar LP-like projection。它证明同一 Jones 候选在 straight-SCF BPM 传播后仍给出高纯 LP11 two-lobe/LP11x-like local projection，但它不替代 Lumerical EME 的 abrupt SCF-FMF interface S-matrix，也不是 RSoft native modal-overlap vendor-certified 结果。

## Updated Key Metrics

| stage | target | decision | eta | captured | rho_group | orientation purity | LP11 ratio dB | LP01 suppression dB |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Lumerical FDE retained proof | strict LP11x-like | `target_mode_generated_revised_gate_proof` | `0.522402` | `0.522402` | `1` | `1` | `70.0654` | `-268.426` |
| Lumerical EME | strict LP11x-like | `lp11x_jones_polarization_eme_feasibility_pass` | `0.646994` | `0.648843` | `1` | `0.99715` | `25.4394` | `-262.597` |
| COMSOL FDE retained | strict LP11x-like | `strict_lp11x_gate_failed` | `0.000251361` | `0.409327` | `0.999757` | `0.000614232` | `-32.114` | `-5.14967` |
| COMSOL FDE retained | LP11 two-lobe symmetry | `lp11_two_lobe_comsol_symmetry_gate_pass_rotated_90deg` | `0.408976` | `0.409327` | `0.999757` | `0.999386` | `32.114` | `-37.2637` |
| COMSOL FDE retained reoptimized | strict LP11x-like | `fallback_jones_lp11x_gate_pass` | `0.519483` | `0.519554` | `0.999867` | `0.999995` | `52.9409` | `-46.6736` |
| RSoft BeamPROP/BPM | LP11 two-lobe / LP11x-like local projection | `rsoft_beamprop_gate_i_feasibility_pass` | `0.638315` | `0.638315` | `1` | `0.999601` | `33.99` | `-136.952` |

## RSoft/BPM Addendum Metrics

- BeamPROP execution status: `all_coarse_and_refined_completed`
- Selected metric set: `refined`
- Gate-I pass: `True`
- eta: `0.638315`
- captured power: `0.638315`
- rho: `1`
- LP11x/LP11y ratio: `33.99 dB`
- LP01 suppression: `-136.952 dB`
- delta_eta_vs_L0: `0.629421`

Claim boundary:

`RSoft BeamPROP scalar/semi-vector BPM feasibility addendum for the locked LP11x-like Jones candidate. It validates reviewed package/execution and, when final fields are available, local scalar LP11 projection diagnostics. It is not a fabricated splice, reflection, taper, robustness, or vendor-certified full-vector modal-overlap validation.`

## Figure Package

This package contains `36` tracked figure rows. Every row is listed in `data/final_report_figure_inventory_with_rsoft_bpm.csv`; copied source availability is recorded per row.

![base_01_evidence_chain](figures/base_01_evidence_chain.png)

*Caption: Original LP11x feasibility evidence chain before the RSoft/BPM addendum; use together with the updated BPM section.*

![base_02_structure_jones_architecture](figures/base_02_structure_jones_architecture.png)

*Caption: Selected p46/SCF86 Jones-polarization architecture and geometry used by the Lumerical/COMSOL feasibility chain.*

![base_03_solver_stage_metrics](figures/base_03_solver_stage_metrics.png)

*Caption: Solver-stage metrics for retained-FDE, Lumerical EME, and COMSOL before adding the RSoft/BPM row.*

![base_04_modal_decomposition](figures/base_04_modal_decomposition.png)

*Caption: LP11x/LP11y-like modal decomposition and cross-solver orientation-convention evidence.*

![base_05_deferred_risk_matrix](figures/base_05_deferred_risk_matrix.png)

*Caption: Deferred robustness, eta optimization, strict cross-solver orientation convention, and fabrication/experiment risk matrix.*

![06_smf_jones_input_summary](figures/06_smf_jones_input_summary.png)

*Caption: SMF Jones input summary from the EME-aware passing input. This documents the 4 physical cores x 2 polarization-channel architecture.*

![07_smf_jones_input_amplitude](figures/07_smf_jones_input_amplitude.png)

*Caption: Per-channel Jones input amplitude. This supports reproducibility of the phase-amplitude-polarization control vector.*

![08_smf_jones_input_phase](figures/08_smf_jones_input_phase.png)

*Caption: Per-channel Jones input phase. This is part of the reproducible EME-aware input definition.*

![09_smf_jones_input_polarization](figures/09_smf_jones_input_polarization.png)

*Caption: Per-core polarization state for the locked Jones input. This figure makes clear that the current pass requires polarization degrees of freedom.*

![10_smf_input_amplitude_phase](figures/10_smf_input_amplitude_phase.png)

*Caption: Retained-FDE field packet: SMF input-plane amplitude and phase for the selected proof row.*

![11_scf_z0_amplitude_phase](figures/11_scf_z0_amplitude_phase.png)

*Caption: Retained-FDE field packet: SCF entrance plane at z=0. This links the SMF input to the SCF retained-basis propagation model.*

![12_scf_zL_amplitude_phase](figures/12_scf_zL_amplitude_phase.png)

*Caption: Retained-FDE field packet: SCF output plane at the selected length. This is the MMI propagation endpoint before FMF projection/interface evidence.*

![13_fmf_output_amplitude_phase](figures/13_fmf_output_amplitude_phase.png)

*Caption: Retained-FDE reconstructed FMF output amplitude and phase. Camera-like appearance is diagnostic; modal metrics remain the success criterion.*

![14_input_channel_amplitude_phase_power](figures/14_input_channel_amplitude_phase_power.png)

*Caption: Selected input-channel amplitude, phase, and power summary for the retained-FDE proof packet.*

![15_polarization_stokes_maps](figures/15_polarization_stokes_maps.png)

*Caption: Polarization/Stokes diagnostic maps from the retained-FDE proof packet. This records polarization evidence, not robustness.*

![16_jones_eme_fmf_output_intensity](figures/16_jones_eme_fmf_output_intensity.png)

*Caption: Lumerical EME strict LP11x-like output intensity from the real S21 plus real cell-1 remap replay.*

![17_comsol_jones_fmf_output_intensity](figures/17_comsol_jones_fmf_output_intensity.png)

*Caption: COMSOL retained-basis replay of the locked EME Jones input. The output is LP11y-like, i.e. a 90-degree rotated LP11 two-lobe symmetry pass.*

![18_comsol_jones_optimized_fmf_output_intensity](figures/18_comsol_jones_optimized_fmf_output_intensity.png)

*Caption: COMSOL retained-basis fallback Jones re-optimization. This confirms the same geometry can support strict LP11x-like output in the COMSOL basis.*

![19_lumerical_raw_mode_field_previews](figures/19_lumerical_raw_mode_field_previews.png)

*Caption: Raw imported Lumerical FDE mode-field previews for SMF, SCF, and FMF datasets used by the locked p46/SCF86/SCF160 evidence chain. This closes the final-report requirement for basis field visibility; it is dataset evidence, not a camera-only success claim.*

![20_length_mmi_gain_and_solver_reconciliation](figures/20_length_mmi_gain_and_solver_reconciliation.png)

*Caption: Length-scan and MMI-gain evidence. The RSoft/BPM panel explicitly compares direct `L=0` launch to the selected propagation length; the reconciliation panel records solver-specific length disagreement rather than hiding it.*

![21_scf_modal_launch_spectrum](figures/21_scf_modal_launch_spectrum.png)

*Caption: SCF retained-mode launch spectrum after the 4-core Jones input is remapped into the EME/FDE cell-1 basis. This is the required SCF modal-concentration evidence for the selected candidate.*

![22_lumerical_basis_validation_summary](figures/22_lumerical_basis_validation_summary.png)

*Caption: Basis validation summary for the imported Lumerical SMF/SCF/FMF vector datasets. This figure records Gram condition, orthogonality, and normalization evidence used by the retained-basis and EME replay chain.*

![23_lumerical_smf_vector_gram](figures/23_lumerical_smf_vector_gram.png)

*Caption: SMF vector-basis Gram heatmap regenerated at final-report resolution from the imported Lumerical NPZ.*

![24_lumerical_scf_vector_gram](figures/24_lumerical_scf_vector_gram.png)

*Caption: SCF160 vector-basis Gram heatmap regenerated at final-report resolution from the imported Lumerical NPZ.*

![25_lumerical_fmf_vector_gram](figures/25_lumerical_fmf_vector_gram.png)

*Caption: FMF12 vector-basis Gram heatmap regenerated at final-report resolution from the imported Lumerical NPZ.*

![27_lumerical_mode_label_projection_stability](figures/27_lumerical_mode_label_projection_stability.png)

*Caption: Mode-label projection stability for the FMF dataset. It separates assigned LP group labels from LP11x/LP11y-like reference projections, preventing camera-only or convention-only claims.*

![28_eme_smatrix_power_budget](figures/28_eme_smatrix_power_budget.png)

*Caption: Power budget from the real Lumerical EME S-matrix replay: LP11x target coupling, non-target LP11 leakage, LP01 leakage, S11 reflection, and untracked/loss. This figure distinguishes interface evidence from retained-FDE propagation evidence.*

![29_revised_gate_robustness_deferred_summary](figures/29_revised_gate_robustness_deferred_summary.png)

*Caption: Existing robustness and tolerance data are visualized as deferred risk. This figure documents known sensitivity without upgrading the current report to a robust-final-validation claim.*

![geometry](figures/rsoft_lp11x_bpm_geometry.png)

*Caption: Geometry and aperture overview for the locked p46/SCF86 LP11x-like Jones candidate. This supports the structure claim only; it is not a modal-success metric.*

![jones_input_controls](figures/rsoft_lp11x_jones_input_controls.png)

*Caption: Normalized 4-core x/y Jones launch amplitudes, phases, and power fractions imported from the EME-aware passing input. This documents the practical control architecture used by the BPM replay.*

![xpol_launch_field](figures/rsoft_lp11x_xpol_launch_field.png)

*Caption: Coherent x-polarized BeamPROP launch mask amplitude and phase. This records input provenance and distinguishes the replay from an amplitude-only Gaussian launch.*

![ypol_launch_field](figures/rsoft_lp11x_ypol_launch_field.png)

*Caption: Coherent y-polarized BeamPROP launch mask amplitude and phase. It is paired with the x-polarized subrun and both are combined by input power fraction.*

![longitudinal_monitor](figures/rsoft_lp11x_longitudinal_monitor.png)

*Caption: RSoft BeamPROP longitudinal monitor from the executed BPM runs. It supports solver-execution evidence but is not by itself a modal pass.*

![final_field_panels](figures/rsoft_lp11x_final_field_panels.png)

*Caption: Parsed final RSoft field panels used for local scalar LP-like projection. The projection is local reviewed evidence, not a vendor-certified native modal-overlap result.*

![modal_power_bars](figures/rsoft_lp11x_modal_power_bars.png)

*Caption: Local scalar LP-group projection power bars from the final BPM field. This figure supports the LP11 two-lobe Gate-I metric claim.*

![gate_metric_summary](figures/rsoft_lp11x_gate_metric_summary.png)

*Caption: Gate-I metric summary for eta, rho, captured power, and MMI gain against L=0. Robustness and native RSoft modal semantics are deferred.*

## Requirement Coverage Audit

| requirement | status | evidence | deferred reason |
|---|---|---|---|
| 0_overview_evidence_chain | `complete_current_status` | base_01_evidence_chain plus refreshed key metrics and artifact index |  |
| 1_structure_architecture | `complete_current_status` | base_02_structure_jones_architecture; RSoft BPM geometry; Jones input figures |  |
| 2_cross_section_field_panels | `complete_current_status` | retained-FDE field packet figures 10-15 plus RSoft final-field panels |  |
| 3_modal_decomposition | `complete_current_status` | base_04_modal_decomposition and RSoft modal power bars |  |
| 4_mmi_gain_length | `complete_current_status` | 20_length_mmi_gain_and_solver_reconciliation plus RSoft direct L=0 delta_eta evidence | Full global length/geometry optimization remains deferred by task scope; current-status MMI evidence is covered. |
| 5_scf_propagation | `complete_current_status` | retained-FDE SCF z=0/z=L panels and RSoft longitudinal monitor |  |
| 6_basis_convergence | `complete_current_status` | 22_lumerical_basis_validation_summary and copied SMF/SCF/FMF Gram heatmaps | Expanded robust convergence sweeps remain future work; current SCF160/FMF12 basis evidence is plotted. |
| 7_input_control | `complete_current_status` | Jones input summary/amplitude/phase/polarization figures and input CSVs |  |
| 8_solver_interface_evidence | `complete_current_status` | EME output intensity, COMSOL output figures, RSoft BPM figures and manifests |  |
| 9_robustness_tolerance | `deferred_recorded` | base_05_deferred_risk_matrix and 29_revised_gate_robustness_deferred_summary | Robustness optimization is intentionally deferred for this feasibility/current-status report. |
## Remaining Limits And Next Decision

- Robustness remains deferred for this refreshed package; existing tolerance studies still show beta/length sensitivity as the dominant risk.
- RSoft/BPM evidence is scalar/semi-vector propagation plus local reviewed projection. Native RSoft mode semantics and a vendor-certified overlap table remain future work.
- Strict LP11x naming across Lumerical/COMSOL/RSoft remains a convention/basis-alignment task because LP11 two-lobe symmetry permits 90-degree rotated LP11y-like evidence.
- The practical next branch should choose one of three paths: final/Notion report refresh, bounded robustness/tolerance optimization, or RSoft native/modal semantics review.

## Reproducibility

- Source final report package: `results/platform_runs/task_a_n4_lp11x_like_camera_two_lobe/outputs/final_result_report`
- Source RSoft/BPM package: `Demo for user/2026-05-22_task_a_n4_lp11x_like_camera_two_lobe/results/rsoft_beamprop_feasibility`
- Refreshed data files are in `data/` and copied figures are in `figures/`.
- Public asset directory target: `task_a_n4_lp11x_jones_final_report_20260525_rsoft_bpm_refresh`.
