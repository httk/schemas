# Index

* **v0.1**
    * **datasets**
        * **[Point groups](v0.1/datasets/pointgroups.md)** (property) - [`https://schemas.httk.org/defs/v0.1/datasets/pointgroups`](https://schemas.httk.org/defs/v0.1/datasets/pointgroups.md)
            
            Ordered table of crystallographic point-group records.
            Each item contains point-group classification, finite point-group operations, conjugacy classes, and real and complex character tables generated from cctbx and spgrep.

        * **[Space groups](v0.1/datasets/spacegroups.md)** (property) - [`https://schemas.httk.org/defs/v0.1/datasets/spacegroups`](https://schemas.httk.org/defs/v0.1/datasets/spacegroups.md)
            
            Ordered table of crystallographic space-group setting records.
            Each item describes one concrete Hall/International Tables setting of a space group, including symbols, classifications, symmetry operations, asymmetric-unit information, Wyckoff positions, and related auxiliary data.
            The companion top-level `indicies.index_hall_entry_to_spacegroups` lookup maps normalized Hall entries to indices in this list; it is not an OPTIMADE property.

        * **[Transformations](v0.1/datasets/transformations.md)** (property) - [`https://schemas.httk.org/defs/v0.1/datasets/transformations`](https://schemas.httk.org/defs/v0.1/datasets/transformations.md)
            
            Ordered table of crystallographic transformation records.
            Each item describes transformations and normalizer information for one concrete International Tables H-M entry.
            In `transformations_hm_entry.json.gz`, items are keyed for lookup by the companion top-level `indicies.index_hm_entry_to_transformations_per_hm_entry` object; that index is not an OPTIMADE property.

    * **derivations**
        * **[Bias](v0.1/derivations/bias.md)** (*[unknown]*) - [`https://schemas.httk.org/defs/v0.1/derivations/bias`](https://schemas.httk.org/defs/v0.1/derivations/bias.md)
            
            The mean signed residual of the base property, predicted minus reference unless stated otherwise.
            The derivation term applies to a base property definition identified alongside; the value has the base property's unit and shape.

        * **[Mean absolute error](v0.1/derivations/mae.md)** (*[unknown]*) - [`https://schemas.httk.org/defs/v0.1/derivations/mae`](https://schemas.httk.org/defs/v0.1/derivations/mae.md)
            
            The mean of the absolute residuals of the base property, predicted minus reference unless stated otherwise.
            The derivation term applies to a base property definition identified alongside; the value has the base property's unit and shape.

        * **[Maximum absolute error](v0.1/derivations/maximum_absolute_error.md)** (*[unknown]*) - [`https://schemas.httk.org/defs/v0.1/derivations/maximum_absolute_error`](https://schemas.httk.org/defs/v0.1/derivations/maximum_absolute_error.md)
            
            The maximum of the absolute residuals of the base property, predicted minus reference unless stated otherwise.
            The derivation term applies to a base property definition identified alongside; the value has the base property's unit and shape.

        * **[Mean](v0.1/derivations/mean.md)** (*[unknown]*) - [`https://schemas.httk.org/defs/v0.1/derivations/mean`](https://schemas.httk.org/defs/v0.1/derivations/mean.md)
            
            The arithmetic mean of independent estimates of the base property.
            The derivation term applies to a base property definition identified alongside; the value has the base property's unit and shape.

        * **[Root-mean-square error](v0.1/derivations/rmse.md)** (*[unknown]*) - [`https://schemas.httk.org/defs/v0.1/derivations/rmse`](https://schemas.httk.org/defs/v0.1/derivations/rmse.md)
            
            The root-mean-square of the signed residuals of the base property, predicted minus reference unless stated otherwise.
            The derivation term applies to a base property definition identified alongside; the value has the base property's unit and shape.

        * **[Standard deviation](v0.1/derivations/standard_deviation.md)** (*[unknown]*) - [`https://schemas.httk.org/defs/v0.1/derivations/standard_deviation`](https://schemas.httk.org/defs/v0.1/derivations/standard_deviation.md)
            
            The sample standard deviation of estimates of the base property, with the degrees-of-freedom correction (ddof) as recorded by the producer.
            The derivation term applies to a base property definition identified alongside; the value has the base property's unit and shape.

        * **[Standard error](v0.1/derivations/standard_error.md)** (*[unknown]*) - [`https://schemas.httk.org/defs/v0.1/derivations/standard_error`](https://schemas.httk.org/defs/v0.1/derivations/standard_error.md)
            
            The standard error of an estimate of the base property: the sample standard deviation of independent estimates divided by the square root of their count. Independence of the estimates is the producer's responsibility.
            The derivation term applies to a base property definition identified alongside; the value has the base property's unit and shape.

    * **entrytypes**
        * **[httk point group symmetry fields](v0.1/entrytypes/pointgroups.md)** (entrytype) - [`https://schemas.httk.org/defs/v0.1/entrytypes/pointgroups`](https://schemas.httk.org/defs/v0.1/entrytypes/pointgroups.md)
            

        * **[httk records entry type](v0.1/entrytypes/records.md)** (entrytype) - [`https://schemas.httk.org/defs/v0.1/entrytypes/records`](https://schemas.httk.org/defs/v0.1/entrytypes/records.md)
            
            A records entry carries the value of one formally declared property (a computed or measured quantity) as its own entry, so that multiple parallel determinations of the same quantity for the same system can coexist as separate entries linked via provenance relationships.
            The value properties served on this entry type are declared per provider through property definitions and are not enumerated here.

        * **[httk runs entry type](v0.1/entrytypes/runs.md)** (entrytype) - [`https://schemas.httk.org/defs/v0.1/entrytypes/runs`](https://schemas.httk.org/defs/v0.1/entrytypes/runs.md)
            
            A runs entry represents one specific, individual execution of a workflow or process that consumed and/or produced other entries.
            Provenance edges (inputs, artifacts, outputs) are expressed as relationships, not properties.

        * **[httk space group symmetry fields](v0.1/entrytypes/spacegroups.md)** (entrytype) - [`https://schemas.httk.org/defs/v0.1/entrytypes/spacegroups`](https://schemas.httk.org/defs/v0.1/entrytypes/spacegroups.md)
            

        * **[httk transformation fields](v0.1/entrytypes/transformations.md)** (entrytype) - [`https://schemas.httk.org/defs/v0.1/entrytypes/transformations`](https://schemas.httk.org/defs/v0.1/entrytypes/transformations.md)
            

    * **properties**
        * **chemistry**
            * **[Species constituent charges](v0.1/properties/chemistry/species_charges.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/chemistry/species_charges`](https://schemas.httk.org/defs/v0.1/properties/chemistry/species_charges.md)
                
                The explicitly assigned charge of each constituent of a species, as a dimensionless charge number, i.e., the charge in units of the elementary charge.

            * **[Species constituent labels](v0.1/properties/chemistry/species_labels.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/chemistry/species_labels`](https://schemas.httk.org/defs/v0.1/properties/chemistry/species_labels.md)
                
                A free-form label attached to each constituent of a species.

            * **[Species constituent spins](v0.1/properties/chemistry/species_spins.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/chemistry/species_spins`](https://schemas.httk.org/defs/v0.1/properties/chemistry/species_spins.md)
                
                The idealized spin assigned to each constituent of a species, as a dimensionless signed number.

            * **[Structure charge](v0.1/properties/chemistry/structure_charge.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/chemistry/structure_charge`](https://schemas.httk.org/defs/v0.1/properties/chemistry/structure_charge.md)
                
                The explicitly assigned net charge of the whole structure, as a dimensionless charge number, i.e., the charge in units of the elementary charge.

        * **core**
            * **[Average total energy](v0.1/properties/core/average_total_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/average_total_energy`](https://schemas.httk.org/defs/v0.1/properties/core/average_total_energy.md)
                
                The total energy of a simulated system averaged over the time evolution of a molecular dynamics run, in electronvolt.
                It is the average the simulation code reports for the run where the code prints one (for example the averages table of a GROMACS md.log); otherwise it is the arithmetic mean of the total energies the code printed over the run's sampled steps.
                The averaging window, the sampling interval and the ensemble are determined by the run, so values are comparable only between runs with the same protocol. The value is for the whole simulated system, kinetic plus potential energy. The reference/zero of the total energy scale is method-, force-field- and code-specific, so values are comparable only within one consistent computational setup.

            * **[Enthalpy](v0.1/properties/core/enthalpy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/enthalpy`](https://schemas.httk.org/defs/v0.1/properties/core/enthalpy.md)
                
                The enthalpy H = E_total + P V in electronvolt, with P the applied (external) pressure and V the cell volume. Extensive: refers to the whole simulated cell, not per atom.
                The reference/zero of the energy scale is method- and code-specific, so values are comparable only within one consistent computational setup.
                A null value means the quantity is not available or not recorded.

            * **[Fraction](v0.1/properties/core/fraction.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/fraction`](https://schemas.httk.org/defs/v0.1/properties/core/fraction.md)
                
                A numerical representation formed as the quotient of two numbers represented as a string.

            * **[Fractional coordinate precision](v0.1/properties/core/fractional_coordinate_precision.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/fractional_coordinate_precision`](https://schemas.httk.org/defs/v0.1/properties/core/fractional_coordinate_precision.md)
                
                The absolute precision of a set of fractional coordinates, in fractional units.

            * **[Kinetic energy](v0.1/properties/core/kinetic_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/kinetic_energy`](https://schemas.httk.org/defs/v0.1/properties/core/kinetic_energy.md)
                
                The nuclear kinetic energy of a system, in electronvolt. Extensive: refers to the whole simulated cell, not per atom.
                A null value means the quantity is not available or not recorded.

            * **[Length precision](v0.1/properties/core/length_precision.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/length_precision`](https://schemas.httk.org/defs/v0.1/properties/core/length_precision.md)
                
                The absolute precision of a stated length, in ångström.

            * **[Potential energy](v0.1/properties/core/potential_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/potential_energy`](https://schemas.httk.org/defs/v0.1/properties/core/potential_energy.md)
                
                The potential energy of a computed system from the energy model, in electronvolt. Extensive: refers to the whole simulated cell, not per atom.
                The reference/zero of the energy scale is method- and code-specific, so values are comparable only within one consistent computational setup.
                A null value means the quantity is not available or not recorded.

            * **[Pressure](v0.1/properties/core/pressure.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/pressure`](https://schemas.httk.org/defs/v0.1/properties/core/pressure.md)
                
                The pressure of a system, in gigapascal (GPa; 1 GPa = 10^9 Pa). Pressure is positive in compression; stress is tensile-positive. For a hydrostatic state P = -tr(sigma)/3.
                A null value means the quantity is not available or not recorded.

            * **[source ID](v0.1/properties/core/source_id.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/source_id`](https://schemas.httk.org/defs/v0.1/properties/core/source_id.md)
                
                The run's identifier in the system that executed it. For httk-workflow jobs, this is the workspace and job identity in the form <workspace_id>:<job_id>. This property participates in httk content identity so re-collecting the same job deduplicates while distinct jobs remain distinct.

            * **[Stress tensor](v0.1/properties/core/stress_tensor.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/stress_tensor`](https://schemas.httk.org/defs/v0.1/properties/core/stress_tensor.md)
                
                The stress tensor of a system in Voigt notation, in gigapascal (GPa). Pressure is positive in compression; stress is tensile-positive. Voigt order [xx, yy, zz, yz, xz, xy].
                A null value means the quantity is not available or not recorded.

            * **[String markups](v0.1/properties/core/string_markups.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/string_markups`](https://schemas.httk.org/defs/v0.1/properties/core/string_markups.md)
                
                Strings with alternate markup and/or encoding for display rendering.

            * **[Temperature](v0.1/properties/core/temperature.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/temperature`](https://schemas.httk.org/defs/v0.1/properties/core/temperature.md)
                
                The temperature of a system, in kelvin.
                A null value means the quantity is not available or not recorded.

            * **[Total energy](v0.1/properties/core/total_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/total_energy`](https://schemas.httk.org/defs/v0.1/properties/core/total_energy.md)
                
                The total energy of a computed system as produced by a calculation, in electronvolt.
                The reference/zero of the total energy scale is method- and code-specific, so values are comparable only within one consistent computational setup.

            * **[Volume](v0.1/properties/core/volume.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/volume`](https://schemas.httk.org/defs/v0.1/properties/core/volume.md)
                
                The volume of the simulation cell, in cubic angstrom. Extensive: refers to the whole simulated cell, not per atom.
                A null value means the quantity is not available or not recorded.

            * **[Workflow declaration URI](v0.1/properties/core/workflow_declaration_uri.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/workflow_declaration_uri`](https://schemas.httk.org/defs/v0.1/properties/core/workflow_declaration_uri.md)
                
                A URI identifying the workflow declaration (the reusable process definition, as opposed to a specific execution) behind a runs entry.
                No particular URI scheme, resolvability, or formalism is mandated.
                Providers wanting two runs recognized as executions of the same declaration MUST use an identical URI.
                Null is expected for ad-hoc scripts, interactive executions, and legacy data with no formal workflow identifier.

            * **[Workflow definition URI](v0.1/properties/core/workflow_definition_uri.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/core/workflow_definition_uri`](https://schemas.httk.org/defs/v0.1/properties/core/workflow_definition_uri.md)
                
                A URI identifying the workflow definition (the code that ran) behind a runs entry, as opposed to the workflow declaration identified by `workflow_declaration_uri`.
                A typical value is a git URI pinned to a full commit hash, of the form `git+https://host/path@<commit>#<subdir>`.
                No particular URI scheme or resolvability is mandated, but providers SHOULD use a URI that pins the exact code revision.
                Null is expected when the executed code is unknown, e.g., for legacy data.

        * **defects**
            * **[Adsorption energy](v0.1/properties/defects/adsorption_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/defects/adsorption_energy`](https://schemas.httk.org/defs/v0.1/properties/defects/adsorption_energy.md)
                
                The adsorption energy E_ads = E(substrate+adsorbate) - E(substrate) - sum_i n_i E_ref,i, in electronvolt, with n_i the numbers of adsorbed atoms or molecules and E_ref,i their reference energies.
                Negative values mean favourable adsorption.
                A null value means the quantity is not available or not recorded.

            * **[Charge transition level](v0.1/properties/defects/charge_transition_level.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/defects/charge_transition_level`](https://schemas.httk.org/defs/v0.1/properties/defects/charge_transition_level.md)
                
                The charge transition level q/q' of one defect, in electronvolt: the Fermi level (relative to the valence-band maximum) at which the formation energies of the two charge states are equal. For a single defect it is independent of the chemical potentials.
                A null value means the quantity is not available or not recorded.

            * **[Charged defect formation energy](v0.1/properties/defects/charged_defect_formation_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/defects/charged_defect_formation_energy`](https://schemas.httk.org/defs/v0.1/properties/defects/charged_defect_formation_energy.md)
                
                The formation energy of a charged point defect in one charge state, in electronvolt, together with all quantities that entered it. List members `elements`, `atom_changes` and `chemical_potentials` are parallel lists sharing the dimension `_httk_dim_elements`, since dictionaries cannot have free-form keys; they MUST have equal length.
                E_f = E_def - E_host - sum_i n_i mu_i + q (E_F + E_VBM + dV) + E_corr.
                A null value means the quantity is not available or not recorded.

            * **[Segregation energy](v0.1/properties/defects/segregation_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/defects/segregation_energy`](https://schemas.httk.org/defs/v0.1/properties/defects/segregation_energy.md)
                
                The segregation energy of a solute, in electronvolt: E(solute at the target site) - E(solute in a bulk-like reference site).
                Negative values mean that segregation to the target site is favoured.
                A null value means the quantity is not available or not recorded.

            * **[Surface energy](v0.1/properties/defects/surface_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/defects/surface_energy`](https://schemas.httk.org/defs/v0.1/properties/defects/surface_energy.md)
                
                The surface energy gamma = (E_slab - N E_bulk - sum_i dn_i mu_i) / A_total, in joule per square metre (J m^-2), with E_bulk the bulk energy per formula-unit-or-atom counted by N, dn_i the excess number of atoms of species i and mu_i their chemical potentials.
                A_total is the total exposed area: both faces of a symmetric slab are counted.
                A null value means the quantity is not available or not recorded.

        * **electronic**
            * **[Band gap](v0.1/properties/electronic/band_gap.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/electronic/band_gap`](https://schemas.httk.org/defs/v0.1/properties/electronic/band_gap.md)
                
                The fundamental band gap in electronvolt: CBM - VBM over the sampled k-points, determined from occupations; indirect gaps are allowed. A metal is represented by the value 0.
                A null value means the quantity is not available or not recorded.

            * **[DFT band gap](v0.1/properties/electronic/dft_band_gap.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/electronic/dft_band_gap`](https://schemas.httk.org/defs/v0.1/properties/electronic/dft_band_gap.md)
                
                The Kohn-Sham band gap of a material from a density-functional-theory (DFT) calculation, given in electronvolts. Its value depends on the computational method and exchange-correlation functional used.

            * **[Direct band gap](v0.1/properties/electronic/direct_band_gap.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/electronic/direct_band_gap`](https://schemas.httk.org/defs/v0.1/properties/electronic/direct_band_gap.md)
                
                The direct band gap in electronvolt: the minimum over the sampled k-points of the CBM - VBM separation at the same k-point, determined from occupations. A metal is represented by the value 0.
                A null value means the quantity is not available or not recorded.

            * **[Electronic density of states](v0.1/properties/electronic/electronic_density_of_states.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/electronic/electronic_density_of_states`](https://schemas.httk.org/defs/v0.1/properties/electronic/electronic_density_of_states.md)
                
                Electronic density of states of a simulation cell.

            * **[Fermi energy](v0.1/properties/electronic/fermi_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/electronic/fermi_energy`](https://schemas.httk.org/defs/v0.1/properties/electronic/fermi_energy.md)
                
                The Fermi energy of a calculation, in electronvolt, on the absolute energy scale of that calculation (the same scale as its eigenvalues and total energy).
                The reference of that scale is method- and code-specific, so values are comparable only within one consistent computational setup.
                A null value means the quantity is not available or not recorded.

            * **[High-frequency relative permittivity](v0.1/properties/electronic/high_frequency_relative_permittivity.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/electronic/high_frequency_relative_permittivity`](https://schemas.httk.org/defs/v0.1/properties/electronic/high_frequency_relative_permittivity.md)
                
                The high-frequency relative permittivity, dimensionless, as the isotropic mean (trace/3) of the high-frequency relative-permittivity tensor, which is the electronic contribution at clamped ions (ions held fixed).
                A null value means the quantity is not available or not recorded.

            * **[Relative effective mass](v0.1/properties/electronic/relative_effective_mass.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/electronic/relative_effective_mass`](https://schemas.httk.org/defs/v0.1/properties/electronic/relative_effective_mass.md)
                
                The effective-mass tensor of one band at the wavevector `center`, relative to the free-electron mass: m*/m_e = m_e^-1 hbar^2 (d^2E/dk_i dk_j)^-1, the inverse of the band-energy curvature matrix at `center`. `center` is in angstrom^-1 (2 pi included); `tensor` is dimensionless.
                The tensor is signed: negative values correspond to hole-like (downward) curvature, and mixed-sign eigenvalues occur at saddle points. Where the curvature matrix is singular the effective mass is undefined and the value is null.
                A null value means the quantity is not available or not recorded.

            * **[Static relative permittivity](v0.1/properties/electronic/static_relative_permittivity.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/electronic/static_relative_permittivity`](https://schemas.httk.org/defs/v0.1/properties/electronic/static_relative_permittivity.md)
                
                The static relative permittivity (dielectric constant), dimensionless, as the isotropic mean (trace/3) of the static relative-permittivity tensor, which includes both the ionic and the electronic contributions.
                A null value means the quantity is not available or not recorded.

        * **energetics**
            * **[Energy above hull per atom](v0.1/properties/energetics/energy_above_hull_per_atom.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/energetics/energy_above_hull_per_atom`](https://schemas.httk.org/defs/v0.1/properties/energetics/energy_above_hull_per_atom.md)
                
                The nonnegative per-atom energy distance, in electronvolt, of a phase to the lower convex hull of the competing phases considered; zero for a phase on the hull. The set of competing phases is part of the producing analysis.
                A null value means the quantity is not available or not recorded.

            * **[Formation energy per atom](v0.1/properties/energetics/formation_energy_per_atom.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/energetics/formation_energy_per_atom`](https://schemas.httk.org/defs/v0.1/properties/energetics/formation_energy_per_atom.md)
                
                The formation energy per atom, (E - sum_i n_i mu_i)/N in electronvolt, with E the total energy of the cell, n_i the number of atoms of element i, mu_i the elemental reservoir chemical potential per atom and N the total number of atoms. The references mu_i are part of the producing analysis and recorded alongside.
                The reference/zero of the energy scale is method- and code-specific, so values are comparable only within one consistent computational setup.
                A null value means the quantity is not available or not recorded.

            * **[Reaction energy](v0.1/properties/energetics/reaction_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/energetics/reaction_energy`](https://schemas.httk.org/defs/v0.1/properties/energetics/reaction_energy.md)
                
                The energy of a reaction in electronvolt, products minus reactants for the balanced reaction as written, weighted by the stoichiometric coefficients of that reaction. Extensive in those coefficients: it refers to the reaction as written, not per atom.
                A null value means the quantity is not available or not recorded.

            * **[Total energy per atom](v0.1/properties/energetics/total_energy_per_atom.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/energetics/total_energy_per_atom`](https://schemas.httk.org/defs/v0.1/properties/energetics/total_energy_per_atom.md)
                
                The total energy of the cell divided by the number of atoms in the cell, in electronvolt.
                The reference/zero of the energy scale is method- and code-specific, as for the total energy, so values are comparable only within one consistent computational setup.
                A null value means the quantity is not available or not recorded.

        * **kinetics**
            * **[Activation energy](v0.1/properties/kinetics/activation_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/kinetics/activation_energy`](https://schemas.httk.org/defs/v0.1/properties/kinetics/activation_energy.md)
                
                The Arrhenius activation energy E_a, in electronvolt, obtained from the slope of ln k against 1/T (k = A exp(-E_a / (k_B T))).
                A null value means the quantity is not available or not recorded.

            * **[Forward migration barrier](v0.1/properties/kinetics/migration_barrier_forward.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/kinetics/migration_barrier_forward`](https://schemas.httk.org/defs/v0.1/properties/kinetics/migration_barrier_forward.md)
                
                The forward migration barrier of a sampled minimum-energy path, in electronvolt: the highest sampled image energy minus the energy of the initial image. No interpolation between images is applied.
                A null value means the quantity is not available or not recorded.

            * **[Reverse migration barrier](v0.1/properties/kinetics/migration_barrier_reverse.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/kinetics/migration_barrier_reverse`](https://schemas.httk.org/defs/v0.1/properties/kinetics/migration_barrier_reverse.md)
                
                The reverse migration barrier of a sampled minimum-energy path, in electronvolt: the highest sampled image energy minus the energy of the final image. No interpolation between images is applied.
                A null value means the quantity is not available or not recorded.

        * **magnetism**
            * **[MAGNDATA identifiers](v0.1/properties/magnetism/magndata_ids.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/magnetism/magndata_ids`](https://schemas.httk.org/defs/v0.1/properties/magnetism/magndata_ids.md)
                
                The identifiers of MAGNDATA magnetic-structure entries associated with a material.

            * **[Magnetic space group (BNS)](v0.1/properties/magnetism/magnetic_space_group_bns.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/magnetism/magnetic_space_group_bns`](https://schemas.httk.org/defs/v0.1/properties/magnetism/magnetic_space_group_bns.md)
                
                The magnetic space group of a material in Belov-Neronova-Smirnova (BNS) notation.

            * **[Site magnetic moments](v0.1/properties/magnetism/site_moments.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/magnetism/site_moments`](https://schemas.httk.org/defs/v0.1/properties/magnetism/site_moments.md)
                
                The magnetic moment vector of each site, in Cartesian coordinates and Bohr magnetons.

            * **[Total magnetic moment](v0.1/properties/magnetism/total_magnetic_moment.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/magnetism/total_magnetic_moment`](https://schemas.httk.org/defs/v0.1/properties/magnetism/total_magnetic_moment.md)
                
                The total magnetic moment of the cell, in Bohr magnetons, as a vector over `dim_spatial`: the vector sum of the site moments in the Cartesian frame of the structure (the frame of `lattice_vectors` and `cartesian_site_positions`).
                Only the sum of the site moments is recorded; contributions outside the sites (interstitial regions) are not included unless the producing analysis states so.
                A null value means the quantity is not available or not recorded.

        * **mechanics**
            * **[Bulk modulus](v0.1/properties/mechanics/bulk_modulus.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus`](https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus.md)
                
                The bulk modulus B = -V dP/dV at the reference state, in gigapascal. The protocol that produced the value (static equation-of-state fit, quasi-harmonic at temperature T, elastic-tensor average) is identified by how it was produced and recorded alongside, not by this definition.
                A null value means the quantity is not available or not recorded.

            * **[Bulk modulus (Hill)](v0.1/properties/mechanics/bulk_modulus_hill.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_hill`](https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_hill.md)
                
                The Hill polycrystalline-average bulk modulus from the elastic tensor, in gigapascal: K_H = (K_V + K_R)/2. Elastic stiffness relates tensor stress to ENGINEERING shear strain (gamma = 2 epsilon), so that sigma_i = C_ij e_j in Voigt form; compliance S = C^-1 in the same convention (S includes the factors 2 and 4 for shear components relative to the tensor compliance).
                A null value means the quantity is not available or not recorded.

            * **[Bulk modulus pressure derivative](v0.1/properties/mechanics/bulk_modulus_pressure_derivative.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_pressure_derivative`](https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_pressure_derivative.md)
                
                The pressure derivative of the bulk modulus, B' = dB/dP at the reference state (dimensionless).
                A null value means the quantity is not available or not recorded.

            * **[Bulk modulus (Reuss)](v0.1/properties/mechanics/bulk_modulus_reuss.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_reuss`](https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_reuss.md)
                
                The Reuss polycrystalline-average bulk modulus from the elastic tensor, in gigapascal: K_R = 1/[(S11+S22+S33) + 2(S12+S13+S23)], with S the compliance tensor. Elastic stiffness relates tensor stress to ENGINEERING shear strain (gamma = 2 epsilon), so that sigma_i = C_ij e_j in Voigt form; compliance S = C^-1 in the same convention (S includes the factors 2 and 4 for shear components relative to the tensor compliance).
                A null value means the quantity is not available or not recorded.

            * **[Bulk modulus (Voigt)](v0.1/properties/mechanics/bulk_modulus_voigt.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_voigt`](https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_voigt.md)
                
                The Voigt polycrystalline-average bulk modulus from the elastic tensor, in gigapascal: K_V = [(C11+C22+C33) + 2(C12+C13+C23)]/9, with C the elastic tensor. Elastic stiffness relates tensor stress to ENGINEERING shear strain (gamma = 2 epsilon), so that sigma_i = C_ij e_j in Voigt form; compliance S = C^-1 in the same convention (S includes the factors 2 and 4 for shear components relative to the tensor compliance).
                A null value means the quantity is not available or not recorded.

            * **[Compliance tensor](v0.1/properties/mechanics/compliance_tensor.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/compliance_tensor`](https://schemas.httk.org/defs/v0.1/properties/mechanics/compliance_tensor.md)
                
                The 6x6 elastic compliance tensor S = C^-1 in Voigt notation, in inverse gigapascal; symmetric. Rows and columns follow Voigt order [xx, yy, zz, yz, xz, xy]. Elastic stiffness relates tensor stress to ENGINEERING shear strain (gamma = 2 epsilon), so that sigma_i = C_ij e_j in Voigt form; compliance S = C^-1 in the same convention (S includes the factors 2 and 4 for shear components relative to the tensor compliance).
                A null value means the quantity is not available or not recorded.

            * **[Elastic tensor](v0.1/properties/mechanics/elastic_tensor.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/elastic_tensor`](https://schemas.httk.org/defs/v0.1/properties/mechanics/elastic_tensor.md)
                
                The 6x6 elastic stiffness tensor C in Voigt notation, in gigapascal; symmetric. Rows and columns follow Voigt order [xx, yy, zz, yz, xz, xy]. Elastic stiffness relates tensor stress to ENGINEERING shear strain (gamma = 2 epsilon), so that sigma_i = C_ij e_j in Voigt form; compliance S = C^-1 in the same convention (S includes the factors 2 and 4 for shear components relative to the tensor compliance).
                At finite pressure this is the stress-strain coefficient tensor (Wallace's B), and stability tests on it use positive definiteness directly.
                A null value means the quantity is not available or not recorded.

            * **[Equilibrium energy](v0.1/properties/mechanics/equilibrium_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/equilibrium_energy`](https://schemas.httk.org/defs/v0.1/properties/mechanics/equilibrium_energy.md)
                
                The minimum of the fitted energy, in electronvolt. Extensive: refers to the whole simulated cell, not per atom.
                The reference/zero of the energy scale is method- and code-specific, so values are comparable only within one consistent computational setup.
                A null value means the quantity is not available or not recorded.

            * **[Equilibrium volume](v0.1/properties/mechanics/equilibrium_volume.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/equilibrium_volume`](https://schemas.httk.org/defs/v0.1/properties/mechanics/equilibrium_volume.md)
                
                The volume that minimizes the fitted energy or free energy, in cubic angstrom. Extensive: refers to the whole simulated cell, not per atom.
                A null value means the quantity is not available or not recorded.

            * **[Shear modulus (Hill)](v0.1/properties/mechanics/shear_modulus_hill.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/shear_modulus_hill`](https://schemas.httk.org/defs/v0.1/properties/mechanics/shear_modulus_hill.md)
                
                The Hill polycrystalline-average shear modulus from the elastic tensor, in gigapascal: G_H = (G_V + G_R)/2. Elastic stiffness relates tensor stress to ENGINEERING shear strain (gamma = 2 epsilon), so that sigma_i = C_ij e_j in Voigt form; compliance S = C^-1 in the same convention (S includes the factors 2 and 4 for shear components relative to the tensor compliance).
                A null value means the quantity is not available or not recorded.

            * **[Shear modulus (Reuss)](v0.1/properties/mechanics/shear_modulus_reuss.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/shear_modulus_reuss`](https://schemas.httk.org/defs/v0.1/properties/mechanics/shear_modulus_reuss.md)
                
                The Reuss polycrystalline-average shear modulus from the elastic tensor, in gigapascal: G_R = 15/[4(S11+S22+S33) - 4(S12+S13+S23) + 3(S44+S55+S66)], with S the compliance tensor. Elastic stiffness relates tensor stress to ENGINEERING shear strain (gamma = 2 epsilon), so that sigma_i = C_ij e_j in Voigt form; compliance S = C^-1 in the same convention (S includes the factors 2 and 4 for shear components relative to the tensor compliance).
                A null value means the quantity is not available or not recorded.

            * **[Shear modulus (Voigt)](v0.1/properties/mechanics/shear_modulus_voigt.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/shear_modulus_voigt`](https://schemas.httk.org/defs/v0.1/properties/mechanics/shear_modulus_voigt.md)
                
                The Voigt polycrystalline-average shear modulus from the elastic tensor, in gigapascal: G_V = [(C11+C22+C33) - (C12+C13+C23) + 3(C44+C55+C66)]/15, with C the elastic tensor. Elastic stiffness relates tensor stress to ENGINEERING shear strain (gamma = 2 epsilon), so that sigma_i = C_ij e_j in Voigt form; compliance S = C^-1 in the same convention (S includes the factors 2 and 4 for shear components relative to the tensor compliance).
                A null value means the quantity is not available or not recorded.

            * **[Universal anisotropy index](v0.1/properties/mechanics/universal_anisotropy_index.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/mechanics/universal_anisotropy_index`](https://schemas.httk.org/defs/v0.1/properties/mechanics/universal_anisotropy_index.md)
                
                The universal elastic anisotropy index A^U = 5 G_V/G_R + K_V/K_R - 6 (dimensionless); zero for an elastically isotropic crystal.
                A null value means the quantity is not available or not recorded.

        * **pointgroups**
            * **[Complex character table](v0.1/properties/pointgroups/character_table_complex.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/character_table_complex`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/character_table_complex.md)
                
                Complex irreducible character table of the crystallographic point group.

            * **[Real character table](v0.1/properties/pointgroups/character_table_real.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/character_table_real`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/character_table_real.md)
                
                Real irreducible character table of the crystallographic point group.

            * **[Conjugacy classes](v0.1/properties/pointgroups/conjugacy_classes.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/conjugacy_classes`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/conjugacy_classes.md)
                
                Conjugacy classes of a crystallographic point group.

            * **[Crystal system](v0.1/properties/pointgroups/crystal_system.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/crystal_system`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/crystal_system.md)
                
                The crystal system of the space group or point group.

            * **[Hermann-Mauguin symbol](v0.1/properties/pointgroups/hm_symbol.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/hm_symbol`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/hm_symbol.md)
                
                Hermann-Mauguin point-group symbol used as the key and display symbol for a point-group record.

            * **[is centrosymmetric](v0.1/properties/pointgroups/is_centrosymmetric.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/is_centrosymmetric`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/is_centrosymmetric.md)
                
                Boolean flag indicating whether the point group contains inversion symmetry.

            * **[Laue class](v0.1/properties/pointgroups/laue_class.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/laue_class`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/laue_class.md)
                
                The Laue class associated with the space group or point group.

            * **[Number of conjugacy classes](v0.1/properties/pointgroups/n_conjugacy_classes.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/n_conjugacy_classes`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/n_conjugacy_classes.md)
                
                Number of conjugacy classes in the crystallographic point group.

            * **[Number of point-group operations](v0.1/properties/pointgroups/n_pointgroup_symops.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/n_pointgroup_symops`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/n_pointgroup_symops.md)
                
                Number of point-group symmetry operations.

            * **[Order of the point group](v0.1/properties/pointgroups/order.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/order`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/order.md)
                
                Order of the point group, i.e. the number of operations in the finite point group.

            * **[Schoenflies symbol](v0.1/properties/pointgroups/schoenflies.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/schoenflies`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/schoenflies.md)
                
                The Schoenflies symbol for the crystallographic point group.

            * **[Schoenflies symbol markups](v0.1/properties/pointgroups/schoenflies_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/schoenflies_markup`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/schoenflies_markup.md)
                
                Display-oriented renderings of the Schoenflies symbol in `schoenflies`.
                The plain string value is stored in the corresponding unsuffixed property; this object only provides alternate markup forms for display.

            * **[Symmetry operations](v0.1/properties/pointgroups/symops.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/symops`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/symops.md)
                
                Full list of symmetry-operation descriptors for a point group.
                Each list member is an `op` object as defined by `/defs/v0.1/properties/symmetry/op`.
                Point-group operations have a zero translation part, so the `screw_glide` and `origin_shift` classification fields are omitted.

        * **spacegroups**
            * **[Asymmetric unit](v0.1/properties/spacegroups/asu.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu.md)
                
                Direct-space asymmetric unit for the space-group setting, represented as a bounded non-recursive set of half-space cuts and boundary ownership rules.

            * **[Asymmetric-unit cut](v0.1/properties/spacegroups/asu_cut.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu_cut`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu_cut.md)
                
                One serialized asymmetric-unit half-space cut or logical cut expression in the recursive cctbx source representation.

            * **[Asymmetric unit markups](v0.1/properties/spacegroups/asu_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu_markup.md)
                
                Display-oriented renderings of the plain-string asymmetric-unit restrictions in `asu_str`.

            * **[Shape-only asymmetric unit markups](v0.1/properties/spacegroups/asu_shape_only_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu_shape_only_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu_shape_only_markup.md)
                
                Display-oriented renderings of the plain-string shape-only asymmetric-unit restrictions in `asu_shape_only_str`.

            * **[Shape-only asymmetric unit string](v0.1/properties/spacegroups/asu_shape_only_str.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu_shape_only_str`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu_shape_only_str.md)
                
                Plain string rendering of the geometric shape part of the asymmetric-unit restrictions, without conditional refinements.

            * **[Asymmetric unit string](v0.1/properties/spacegroups/asu_str.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu_str`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/asu_str.md)
                
                Plain string rendering of the asymmetric-unit restrictions for the space-group setting.

            * **[Bravais type](v0.1/properties/spacegroups/bravais_type.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/bravais_type`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/bravais_type.md)
                
                The Bravais type of the translational lattice.

            * **[cctbx FFT grid factors](v0.1/properties/spacegroups/cctbx_fft_grid_factors.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/cctbx_fft_grid_factors`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/cctbx_fft_grid_factors.md)
                
                FFT grid-factor requirements derived from cctbx for the space group, its structure seminvariants, and its Euclidean normalizer.

            * **[Centering translations](v0.1/properties/spacegroups/centering_translations.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/centering_translations`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/centering_translations.md)
                
                Centering translations of the conventional cell.

            * **[Centring type](v0.1/properties/spacegroups/centring_type.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/centring_type`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/centring_type.md)
                
                The lattice centring symbol for the crystallographic setting.

            * **[Crystal system](v0.1/properties/spacegroups/crystal_system.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/crystal_system`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/crystal_system.md)
                
                The crystal system of the space group or point group.

            * **[Hall symbol](v0.1/properties/spacegroups/hall.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall.md)
                
                The Hall symbol for a crystallographic space-group setting.

            * **[Hall symbol aliases](v0.1/properties/spacegroups/hall_aliases.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall_aliases`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall_aliases.md)
                
                Alternate ASCII Hall symbols or Hall-setting keys associated with the same generated setting.

            * **[Hall alias markups](v0.1/properties/spacegroups/hall_aliases_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall_aliases_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall_aliases_markup.md)
                
                Display-oriented renderings corresponding element-by-element to the alternate Hall symbols in `hall_aliases`.

            * **[Hall entry](v0.1/properties/spacegroups/hall_entry.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall_entry`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall_entry.md)
                
                Normalized Hall-table entry key used internally by the generated datasets.

            * **[Hall symbol markups](v0.1/properties/spacegroups/hall_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall_markup.md)
                
                Display-oriented renderings of the Hall symbol in `hall`.

            * **[Harker planes](v0.1/properties/spacegroups/harker_planes.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/harker_planes`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/harker_planes.md)
                
                Harker planes of the space group in fractional Patterson coordinates.

            * **[Universal cctbx Hermann-Mauguin symbol](v0.1/properties/spacegroups/hm_cctbx_universal.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_cctbx_universal`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_cctbx_universal.md)
                
                Universal Hermann-Mauguin symbol returned by cctbx for this setting.

            * **[Hermann-Mauguin entry](v0.1/properties/spacegroups/hm_entry.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_entry`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_entry.md)
                
                The Hermann-Mauguin entry label for a conventional space-group setting from table A1.4.2.7 of the [International Tables for Crystallography (2006). Volume B, Reciprocal space. ISBN: 978-0-7923-6592-1, doi:10.1107/97809553602060000102](https://doi.org/10.1107/97809553602060000102).

            * **[Hermann-Mauguin entry aliases](v0.1/properties/spacegroups/hm_entry_aliases.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_entry_aliases`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_entry_aliases.md)
                
                Alternative Hermann-Mauguin entry labels from International Tables for Crystallography Volume B table A1.4.2.7 that identify the same generated Hall-symbol row as `hm_entry`.

            * **[Hermann-Mauguin entry markups](v0.1/properties/spacegroups/hm_entry_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_entry_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_entry_markup.md)
                
                Display-oriented renderings of the Hermann-Mauguin entry label in `hm_entry`.

            * **[Extended Hermann-Mauguin symbol](v0.1/properties/spacegroups/hm_extended.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_extended`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_extended.md)
                
                The setting-specific extended Hermann-Mauguin symbol for the space-group setting.

            * **[Extended Hermann-Mauguin symbol aliases](v0.1/properties/spacegroups/hm_extended_aliases.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_extended_aliases`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_extended_aliases.md)
                
                Alternate ASCII forms of `hm_extended` that are accepted for the same generated setting.

            * **[Extended Hermann-Mauguin alias markups](v0.1/properties/spacegroups/hm_extended_aliases_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_extended_aliases_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_extended_aliases_markup.md)
                
                Display-oriented renderings corresponding element-by-element to the alternate extended Hermann-Mauguin symbols in `hm_extended_aliases`.

            * **[Extended Hermann-Mauguin symbol markups](v0.1/properties/spacegroups/hm_extended_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_extended_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_extended_markup.md)
                
                Display-oriented renderings of the extended Hermann-Mauguin symbol in `hm_extended`.

            * **[Extended Hermann-Mauguin symbol in old notation](v0.1/properties/spacegroups/hm_extended_old.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_extended_old`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_extended_old.md)
                
                The older extended Hermann-Mauguin symbol retained as an alias for symbols superseded by newer `e`-glide notation.

            * **[Full Hermann-Mauguin symbol](v0.1/properties/spacegroups/hm_full.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full.md)
                
                The setting-specific full Hermann-Mauguin symbol for the space-group setting.

            * **[Full Hermann-Mauguin symbol aliases](v0.1/properties/spacegroups/hm_full_aliases.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_aliases`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_aliases.md)
                
                Alternate ASCII forms of `hm_full` that are accepted for the same generated setting.

            * **[Full Hermann-Mauguin alias markups](v0.1/properties/spacegroups/hm_full_aliases_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_aliases_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_aliases_markup.md)
                
                Display-oriented renderings corresponding element-by-element to the alternate full Hermann-Mauguin symbols in `hm_full_aliases`.

            * **[Full Hermann-Mauguin symbol markups](v0.1/properties/spacegroups/hm_full_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_markup.md)
                
                Display-oriented renderings of the setting-specific full Hermann-Mauguin symbol in `hm_full`.

            * **[Full Hermann-Mauguin symbol in old notation](v0.1/properties/spacegroups/hm_full_old.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_old`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_old.md)
                
                The older full Hermann-Mauguin symbol retained as an alias for symbols superseded by newer `e`-glide notation.

            * **[Standard full Hermann-Mauguin symbol](v0.1/properties/spacegroups/hm_full_std.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_std`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_std.md)
                
                The International Tables standard full Hermann-Mauguin symbol for the space-group type.

            * **[Standard full Hermann-Mauguin symbol markups](v0.1/properties/spacegroups/hm_full_std_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_std_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_full_std_markup.md)
                
                Display-oriented renderings of the ITA-standard full Hermann-Mauguin symbol in `hm_full_std`.

            * **[Short Hermann-Mauguin symbol](v0.1/properties/spacegroups/hm_short.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short.md)
                
                The setting-specific short Hermann-Mauguin symbol for the space-group setting.

            * **[Short Hermann-Mauguin symbol aliases](v0.1/properties/spacegroups/hm_short_aliases.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_aliases`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_aliases.md)
                
                Alternate ASCII forms of `hm_short` that are accepted for the same generated setting.

            * **[Short Hermann-Mauguin alias markups](v0.1/properties/spacegroups/hm_short_aliases_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_aliases_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_aliases_markup.md)
                
                Display-oriented renderings corresponding element-by-element to the alternate short Hermann-Mauguin symbols in `hm_short_aliases`.

            * **[Short Hermann-Mauguin symbol markups](v0.1/properties/spacegroups/hm_short_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_markup.md)
                
                Display-oriented renderings of the setting-specific short Hermann-Mauguin symbol in `hm_short`.

            * **[Short Hermann-Mauguin symbol in old notation](v0.1/properties/spacegroups/hm_short_old.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_old`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_old.md)
                
                The older short Hermann-Mauguin symbol retained as an alias for symbols superseded by newer `e`-glide notation.

            * **[Standard short Hermann-Mauguin symbol](v0.1/properties/spacegroups/hm_short_std.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_std`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_std.md)
                
                The International Tables standard short Hermann-Mauguin symbol for the space-group type.

            * **[Standard short Hermann-Mauguin symbol markups](v0.1/properties/spacegroups/hm_short_std_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_std_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/hm_short_std_markup.md)
                
                Display-oriented renderings of the ITA-standard short Hermann-Mauguin symbol in `hm_short_std`.

            * **[is centric](v0.1/properties/spacegroups/is_centric.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_centric`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_centric.md)
                
                Whether the space group contains an inversion operation `(W,w)` with `W = -I`.
                The inversion center need not be the coordinate origin; one such center is at `w/2` in fractional coordinates.
                This tests the space-group symmetry, not the centricity of an individual diffraction reflection.

            * **[is chiral](v0.1/properties/spacegroups/is_chiral.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_chiral`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_chiral.md)
                
                Whether every operation of the space group preserves handedness, i.e. every linear part has determinant +1.
                This is cctbx's `is_chiral()` convention and identifies the 65 Sohncke space-group types, excluding mirrors, inversion, glide reflections, and rotoinversions.
                It does not mean that the space-group type belongs to one of the 11 enantiomorphic pairs; that is recorded by `is_enantiomorphic`.
                It does not by itself determine the handedness or chirality of a molecular motif.

            * **[is enantiomorphic](v0.1/properties/spacegroups/is_enantiomorphic.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_enantiomorphic`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_enantiomorphic.md)
                
                Boolean flag indicating whether the space-group type belongs to an enantiomorphic pair.

            * **[is reference setting](v0.1/properties/spacegroups/is_reference_setting.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_reference_setting`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_reference_setting.md)
                
                Whether cctbx identifies this Hall setting as its reference setting for the space-group type.
                This is the reference used by cctbx's change-of-basis machinery; it must not be inferred solely from the setting-specific Hermann-Mauguin symbol.
                For the pipeline's selected IT-standard setting, use `index_it_number_to_std_spacegroups` in the dataset's companion `indicies` structure.

            * **[International Tables coordinate-system code](v0.1/properties/spacegroups/it_coordinate_system_code.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/it_coordinate_system_code`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/it_coordinate_system_code.md)
                
                The International Tables coordinate-system code for the setting.

            * **[International Tables space-group number](v0.1/properties/spacegroups/it_number.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/it_number`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/it_number.md)
                
                The International Tables space-group number.

            * **[International Tables number of the enantiomorph](v0.1/properties/spacegroups/it_number_enantiomorphic.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/it_number_enantiomorphic`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/it_number_enantiomorphic.md)
                
                International Tables number of the enantiomorphic partner space group, when one exists.

            * **[Laue class](v0.1/properties/spacegroups/laue_class.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/laue_class`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/laue_class.md)
                
                The Laue class associated with the space group or point group.

            * **[Number of centering translations](v0.1/properties/spacegroups/n_centering_translations.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/n_centering_translations`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/n_centering_translations.md)
                
                Number of centering translations in the conventional cell of the space-group setting.

            * **[Number of point-group operations](v0.1/properties/spacegroups/n_pointgroup_symops.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/n_pointgroup_symops`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/n_pointgroup_symops.md)
                
                Number of point-group symmetry operations.

            * **[Number of symops](v0.1/properties/spacegroups/n_symops.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/n_symops`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/n_symops.md)
                
                Number of symmetry operations in the finite operation list of the generated entry.

            * **[Point-group Hermann-Mauguin symbol](v0.1/properties/spacegroups/point_group.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/point_group`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/point_group.md)
                
                The Hermann-Mauguin point-group symbol for the crystallographic point group of the space group.

            * **[Schoenflies symbol](v0.1/properties/spacegroups/schoenflies.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/schoenflies`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/schoenflies.md)
                
                The Schoenflies symbol for the space-group type.

            * **[Schoenflies symbol markups](v0.1/properties/spacegroups/schoenflies_markup.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/schoenflies_markup`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/schoenflies_markup.md)
                
                Display-oriented renderings of the space-group Schoenflies symbol in `schoenflies`.
                The plain string value is stored in the corresponding unsuffixed property; this object only provides alternate markup forms for display.

            * **[Setting annotation](v0.1/properties/spacegroups/setting.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/setting`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/setting.md)
                
                Setting suffix or setting annotation extracted from the cctbx universal Hermann-Mauguin symbol in `hm_cctbx_universal`.

            * **[International Tables setting code n:c](v0.1/properties/spacegroups/setting_it_nc.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/setting_it_nc`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/setting_it_nc.md)
                
                International Tables setting identifier in `n:c` notation.

            * **[International Tables setting-code aliases](v0.1/properties/spacegroups/setting_it_nc_aliases.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/setting_it_nc_aliases`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/setting_it_nc_aliases.md)
                
                A list of International Tables `n:c` setting identifiers that are alternatives to the one designated as the main one.

            * **[Setting plaintext](v0.1/properties/spacegroups/setting_plaintext.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/setting_plaintext`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/setting_plaintext.md)
                
                Human-readable description of the International Tables coordinate-system setting.

            * **[Space-group symbols](v0.1/properties/spacegroups/spacegroup_symbols.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/spacegroup_symbols`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/spacegroup_symbols.md)
                
                Ordered table of conventional space-group symbol rows.

            * **[Spglib Hall symbol](v0.1/properties/spacegroups/spglib_hall.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/spglib_hall`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/spglib_hall.md)
                
                The Hall symbol for this setting as spelled by the spglib library.

            * **[Spglib Hall numbers](v0.1/properties/spacegroups/spglib_hall_numbers.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/spglib_hall_numbers`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/spglib_hall_numbers.md)
                
                The spglib Hall numbers corresponding to this Hall setting.

            * **[Structure seminvariants](v0.1/properties/spacegroups/structure_seminvariants.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/structure_seminvariants`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/structure_seminvariants.md)
                
                Structure-seminvariant vectors and moduli for the space-group setting, describing allowed changes of origin that preserve its symmetry description.

            * **[Symmetry operations](v0.1/properties/spacegroups/symops.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/symops`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/symops.md)
                
                Full list of symmetry-operation descriptors for a space-group setting.

            * **[Symmetry operation generators](v0.1/properties/spacegroups/symops_generators.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/symops_generators`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/symops_generators.md)
                
                Generator subset of the finite symmetry-operation list for a space-group setting.
                Composition of these operations, with translations reduced modulo integer cell translations, generates `symops`, including the centering translations.
                Integer cell translations are implicit generators of the infinite space group.
                The generator selects operations greedily; the list is not promised to have the smallest possible cardinality.
                Identity is omitted, so the P1 list is empty.

            * **[Symmetry operations modulo centering translations](v0.1/properties/spacegroups/symops_mod_centering.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/symops_mod_centering`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/symops_mod_centering.md)
                
                Representative symmetry-operation descriptors modulo centering translations.

            * **[Representative symmetry operations](v0.1/properties/spacegroups/symops_representative.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/symops_representative`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/symops_representative.md)
                
                Representative symmetry-operation descriptors modulo centering translations: one full-group operation (including inversion-related operations where present) per coset of the centring translations.

            * **[Wyckoff positions](v0.1/properties/spacegroups/wyckoff.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/wyckoff`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/wyckoff.md)
                
                Wyckoff-position table for a specific space-group setting.

            * **[Wyckoff sets](v0.1/properties/spacegroups/wyckoff_sets.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/wyckoff_sets`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/wyckoff_sets.md)
                
                Sets of Wyckoff letters related by normalizer operations.

        * **structure**
            * **[Radial distribution function](v0.1/properties/structure/radial_distribution_function.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/structure/radial_distribution_function`](https://schemas.httk.org/defs/v0.1/properties/structure/radial_distribution_function.md)
                
                Radial distribution function g(r) of a structure or trajectory, binned in distance.

        * **symmetry**
            * **[Affine transformation](v0.1/properties/symmetry/affine_transformation.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/symmetry/affine_transformation`](https://schemas.httk.org/defs/v0.1/properties/symmetry/affine_transformation.md)
                
                An affine transformation acting on fractional crystallographic coordinates.

            * **[Basis transformation](v0.1/properties/symmetry/basis_transform.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/symmetry/basis_transform`](https://schemas.httk.org/defs/v0.1/properties/symmetry/basis_transform.md)
                
                One crystallographic transform between coordinate descriptions, settings, cells, or related group embeddings.

            * **[Centering translation](v0.1/properties/symmetry/centering_translation.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/symmetry/centering_translation`](https://schemas.httk.org/defs/v0.1/properties/symmetry/centering_translation.md)
                
                One centering translation of a conventional crystallographic cell.

            * **[Operation](v0.1/properties/symmetry/op.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/symmetry/op`](https://schemas.httk.org/defs/v0.1/properties/symmetry/op.md)
                
                Information related to a crystallographic operation acting within one coordinate setting.

            * **[Operation xyz](v0.1/properties/symmetry/op_xyz.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/symmetry/op_xyz`](https://schemas.httk.org/defs/v0.1/properties/symmetry/op_xyz.md)
                
                Coordinate operation expressed in the algebraic xyz form, also known as Jones' faithful representation (Bradley & Cracknell, 1972: pp. 35-37; adapted for computer strings).

            * **[Wyckoff position](v0.1/properties/symmetry/wyckoff_position.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/symmetry/wyckoff_position`](https://schemas.httk.org/defs/v0.1/properties/symmetry/wyckoff_position.md)
                
                Information related to a Wyckoff position in a space-group setting.

        * **thermodynamics**
            * **[Heat capacity at constant pressure](v0.1/properties/thermodynamics/heat_capacity_constant_pressure.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/heat_capacity_constant_pressure`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/heat_capacity_constant_pressure.md)
                
                The heat capacity at constant pressure C_P, in electronvolt per kelvin (eV K^-1).
                Extensive quantity of the whole simulated cell. It may be obtained, e.g., from enthalpy fluctuations in the isothermal-isobaric ensemble as Var(H) / (kB T^2), at the temperature recorded alongside.
                A null value means the quantity is not available or not recorded.

            * **[Heat capacity at constant volume](v0.1/properties/thermodynamics/heat_capacity_constant_volume.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/heat_capacity_constant_volume`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/heat_capacity_constant_volume.md)
                
                The heat capacity at constant volume C_V, in electronvolt per kelvin (eV K^-1).
                Extensive quantity of the whole simulated cell. It may be obtained, e.g., from canonical-ensemble energy fluctuations as Var(E) / (kB T^2), at the temperature recorded alongside.
                A null value means the quantity is not available or not recorded.

            * **[Helmholtz free energy](v0.1/properties/thermodynamics/helmholtz_free_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/helmholtz_free_energy`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/helmholtz_free_energy.md)
                
                The Helmholtz free energy F = U - T S, in electronvolt (eV), for the vibrational modes of the referenced cell, at the temperature recorded alongside.
                Extensive quantity of the whole simulated cell. For harmonic phonons F = sum over modes of [h nu / 2 + kB T ln(1 - exp(-h nu / (kB T)))].
                The energy zero is the static (potential) energy of the referenced cell, which is not included.
                A null value means the quantity is not available or not recorded.

            * **[Isothermal compressibility](v0.1/properties/thermodynamics/isothermal_compressibility.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/isothermal_compressibility`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/isothermal_compressibility.md)
                
                The isothermal compressibility kappa_T = -(1/V) (dV/dP)_T, in inverse gigapascal (GPa^-1; 1 GPa = 10^9 Pa).
                It is an intensive quantity of the referenced cell, at the temperature and pressure recorded alongside.
                A null value means the quantity is not available or not recorded.

            * **[Quasiharmonic thermodynamics](v0.1/properties/thermodynamics/quasiharmonic_thermodynamics.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/quasiharmonic_thermodynamics`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/quasiharmonic_thermodynamics.md)
                
                Quasiharmonic equilibrium properties as a function of temperature at zero pressure.

            * **[Vibrational entropy](v0.1/properties/thermodynamics/vibrational_entropy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/vibrational_entropy`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/vibrational_entropy.md)
                
                The vibrational entropy, in electronvolt per kelvin (eV K^-1), for the vibrational modes of the referenced cell, at the temperature recorded alongside.
                Extensive quantity of the whole simulated cell.
                A null value means the quantity is not available or not recorded.

            * **[Vibrational heat capacity](v0.1/properties/thermodynamics/vibrational_heat_capacity.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/vibrational_heat_capacity`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/vibrational_heat_capacity.md)
                
                The harmonic constant-volume heat capacity, in electronvolt per kelvin (eV K^-1), for the vibrational modes of the referenced cell, at the temperature recorded alongside.
                Extensive quantity of the whole simulated cell.
                A null value means the quantity is not available or not recorded.

            * **[Vibrational internal energy](v0.1/properties/thermodynamics/vibrational_internal_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/vibrational_internal_energy`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/vibrational_internal_energy.md)
                
                The vibrational internal energy, in electronvolt (eV), for the vibrational modes of the referenced cell, at the temperature recorded alongside.
                Extensive quantity of the whole simulated cell. It includes the zero-point energy.
                A null value means the quantity is not available or not recorded.

            * **[Vibrational thermodynamics](v0.1/properties/thermodynamics/vibrational_thermodynamics.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/vibrational_thermodynamics`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/vibrational_thermodynamics.md)
                
                Harmonic phonon thermodynamics of the vibrational modes of the referenced cell, tabulated as a function of temperature.

            * **[Volumetric thermal expansion](v0.1/properties/thermodynamics/volumetric_thermal_expansion.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/volumetric_thermal_expansion`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/volumetric_thermal_expansion.md)
                
                The volumetric thermal expansion coefficient alpha_V = (1/V) (dV/dT)_P, in inverse kelvin (K^-1).
                It is the volumetric (not linear) coefficient, an intensive quantity of the referenced cell, at the pressure recorded alongside.
                A null value means the quantity is not available or not recorded.

            * **[Zero-point energy](v0.1/properties/thermodynamics/zero_point_energy.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/thermodynamics/zero_point_energy`](https://schemas.httk.org/defs/v0.1/properties/thermodynamics/zero_point_energy.md)
                
                The zero-point energy, sum over modes of h nu / 2, in electronvolt (eV), for the vibrational modes of the referenced cell.
                Extensive quantity of the whole simulated cell. Temperature independent.
                A null value means the quantity is not available or not recorded.

        * **trajectories**
            * **[Frame stresses](v0.1/properties/trajectories/frame_stresses.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/trajectories/frame_stresses`](https://schemas.httk.org/defs/v0.1/properties/trajectories/frame_stresses.md)
                
                The stress tensor of each frame of a trajectory, aligned with the trajectory frame axis (`dim_frames`).
                Each tensor is given in Voigt order [xx, yy, zz, yz, xz, xy], with tensile stress positive, in gigapascal (GPa; 1 GPa = 10^9 Pa).
                A `null` value indicates that the stress tensor of the corresponding frame is unknown.

            * **[Frame temperatures](v0.1/properties/trajectories/frame_temperatures.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/trajectories/frame_temperatures`](https://schemas.httk.org/defs/v0.1/properties/trajectories/frame_temperatures.md)
                
                The instantaneous temperature of each frame of a trajectory, in kelvin, aligned with the trajectory frame axis (`dim_frames`).
                A `null` value indicates that the temperature of the corresponding frame is unknown.

            * **[Frame total energies](v0.1/properties/trajectories/frame_total_energies.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/trajectories/frame_total_energies`](https://schemas.httk.org/defs/v0.1/properties/trajectories/frame_total_energies.md)
                
                The total energy of each frame of a trajectory, in electronvolt, aligned with the trajectory frame axis (`dim_frames`).
                A `null` value indicates that the energy of the corresponding frame is unknown.
                The reference/zero of the total energy scale is method- and code-specific, so values are comparable only within one consistent computational setup.

            * **[Time step](v0.1/properties/trajectories/time_step.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/trajectories/time_step`](https://schemas.httk.org/defs/v0.1/properties/trajectories/time_step.md)
                
                The molecular-dynamics integration time step between consecutive frames, in femtosecond (fs; 1 fs = 10^-15 s).
                A `null` value indicates that the time step is unknown.

        * **transformations**
            * **[Affine images](v0.1/properties/transformations/affine_images.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/affine_images`](https://schemas.httk.org/defs/v0.1/properties/transformations/affine_images.md)
                
                Same-space-group affine images for a standard setting.

            * **[Affine normalizer](v0.1/properties/transformations/affine_normalizer.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/affine_normalizer`](https://schemas.httk.org/defs/v0.1/properties/transformations/affine_normalizer.md)
                
                Affine normalizer coset representatives for one crystallographic space-group setting.

            * **[Affine normalizer coset data](v0.1/properties/transformations/affine_normalizer_coset_data.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/affine_normalizer_coset_data`](https://schemas.httk.org/defs/v0.1/properties/transformations/affine_normalizer_coset_data.md)
                
                Ordered table of bounded affine normalizer coset-representative data for crystallographic space groups, with one item for each Hall setting.

            * **[Affine normalizer cosets](v0.1/properties/transformations/affine_normalizer_cosets.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/affine_normalizer_cosets`](https://schemas.httk.org/defs/v0.1/properties/transformations/affine_normalizer_cosets.md)
                
                Runtime list of bounded affine normalizer coset representatives modulo the space group.

            * **[Backward lift criteria](v0.1/properties/transformations/backward_lift_criteria.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/backward_lift_criteria`](https://schemas.httk.org/defs/v0.1/properties/transformations/backward_lift_criteria.md)
                
                Criteria table for one supergroup IT number used to lift occupied Wyckoff data from a subgroup back to that supergroup along a chosen Bärnighausen transform.

            * **[Bärnighausen subgroup transforms](v0.1/properties/transformations/baernighausen.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/baernighausen`](https://schemas.httk.org/defs/v0.1/properties/transformations/baernighausen.md)
                
                Bärnighausen subgroup transform table for one parent setting or space-group type.

            * **[Continuous normalizer](v0.1/properties/transformations/continuous_normalizer.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/continuous_normalizer`](https://schemas.httk.org/defs/v0.1/properties/transformations/continuous_normalizer.md)
                
                Parameterized continuous normalizer subspace for a setting.

            * **[Euclidean normalizer](v0.1/properties/transformations/euclidean_normalizer.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/euclidean_normalizer`](https://schemas.httk.org/defs/v0.1/properties/transformations/euclidean_normalizer.md)
                
                Finite Euclidean normalizer operations for one crystallographic space-group setting.

            * **[Hall to IT standard transform](v0.1/properties/transformations/hall_to_it_std_transform.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/hall_to_it_std_transform`](https://schemas.httk.org/defs/v0.1/properties/transformations/hall_to_it_std_transform.md)
                
                Exact basis and origin transform from one stored Hall setting to the International Tables standard Hall setting of the same space-group type.

            * **[Subgroup or transform index](v0.1/properties/transformations/index.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/index`](https://schemas.httk.org/defs/v0.1/properties/transformations/index.md)
                
                Subgroup or transform index.

            * **[Isomorphic subgroup transforms](v0.1/properties/transformations/isomorphic_subgroups.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/isomorphic_subgroups`](https://schemas.httk.org/defs/v0.1/properties/transformations/isomorphic_subgroups.md)
                
                Isomorphic subgroup transforms of bounded index for one parent setting or space-group type.

            * **[Klassengleiche subgroup subtype](v0.1/properties/transformations/k_subtype.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/k_subtype`](https://schemas.httk.org/defs/v0.1/properties/transformations/k_subtype.md)
                
                Subtype of a klassengleiche (`k`) subgroup relation.

            * **[Maximal subgroup relations](v0.1/properties/transformations/maximal_subgroup_relations.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/maximal_subgroup_relations`](https://schemas.httk.org/defs/v0.1/properties/transformations/maximal_subgroup_relations.md)
                
                Maximal non-isomorphic subgroup relations for International Tables space-group types.

            * **[Number of coset representatives](v0.1/properties/transformations/n_coset_representatives.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/n_coset_representatives`](https://schemas.httk.org/defs/v0.1/properties/transformations/n_coset_representatives.md)
                
                Number of nontrivial coset representatives retained after deduplication modulo the space group.

            * **[Number of cosets](v0.1/properties/transformations/n_cosets.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/n_cosets`](https://schemas.httk.org/defs/v0.1/properties/transformations/n_cosets.md)
                
                Number of affine normalizer coset representatives stored for the setting.

            * **[Number of linear parts](v0.1/properties/transformations/n_linear_parts.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/n_linear_parts`](https://schemas.httk.org/defs/v0.1/properties/transformations/n_linear_parts.md)
                
                Number of distinct linear matrix parts represented in a normalizer or transform table.

            * **[Number of orthogonal cosets](v0.1/properties/transformations/n_orthogonal_cosets.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/n_orthogonal_cosets`](https://schemas.httk.org/defs/v0.1/properties/transformations/n_orthogonal_cosets.md)
                
                Number of orthogonal affine normalizer coset representatives stored for the setting.

            * **[Number of raw candidates](v0.1/properties/transformations/n_raw_candidates.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/n_raw_candidates`](https://schemas.httk.org/defs/v0.1/properties/transformations/n_raw_candidates.md)
                
                Number of accepted affine normalizer candidates generated before quotienting modulo the space group and before metric filtering.
                This is not the number of all linear matrices tested: candidates whose affine normalization equations have no solution are not counted.

            * **[Number of unique candidates](v0.1/properties/transformations/n_unique_candidates.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/n_unique_candidates`](https://schemas.httk.org/defs/v0.1/properties/transformations/n_unique_candidates.md)
                
                Number of candidate affine operations remaining after exact duplicate removal.

            * **[Orthogonal affine normalizer](v0.1/properties/transformations/orthogonal_affine_normalizer.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/orthogonal_affine_normalizer`](https://schemas.httk.org/defs/v0.1/properties/transformations/orthogonal_affine_normalizer.md)
                
                Orthogonal affine normalizer coset representatives for one crystallographic space-group setting.

            * **[Orthogonal affine normalizer cosets](v0.1/properties/transformations/orthogonal_affine_normalizer_cosets.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/orthogonal_affine_normalizer_cosets`](https://schemas.httk.org/defs/v0.1/properties/transformations/orthogonal_affine_normalizer_cosets.md)
                
                Runtime list of orthogonal signed-permutation affine normalizer coset representatives modulo the space group.

            * **[Same-space-group affine images in the standard setting](v0.1/properties/transformations/same_space_group_affine_images_std.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/same_space_group_affine_images_std`](https://schemas.httk.org/defs/v0.1/properties/transformations/same_space_group_affine_images_std.md)
                
                Same-space-group affine-image record for one International Tables standard setting.

            * **[Maximal subgroup type](v0.1/properties/transformations/subgroup_type.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/subgroup_type`](https://schemas.httk.org/defs/v0.1/properties/transformations/subgroup_type.md)
                
                International Tables maximal subgroup class.

            * **[Criterion target](v0.1/properties/transformations/target.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/target`](https://schemas.httk.org/defs/v0.1/properties/transformations/target.md)
                
                Exact right-hand side of a generated modular linear criterion, stored as a list of fraction strings.

            * **[To Hall entry](v0.1/properties/transformations/to_hall_entry.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/to_hall_entry`](https://schemas.httk.org/defs/v0.1/properties/transformations/to_hall_entry.md)
                
                Target Hall-entry key to which a setting transform maps the current Hall setting.

            * **[Transformations per H-M entry](v0.1/properties/transformations/transformations_per_hm_entry.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/transformations_per_hm_entry`](https://schemas.httk.org/defs/v0.1/properties/transformations/transformations_per_hm_entry.md)
                
                Transformation data grouped by H-M entry.

            * **[Transformations per IT number](v0.1/properties/transformations/transformations_per_it_number.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/transformations_per_it_number`](https://schemas.httk.org/defs/v0.1/properties/transformations/transformations_per_it_number.md)
                
                Standard-setting transformation data grouped by International Tables space-group number.

            * **[Wyckoff splitting](v0.1/properties/transformations/wyckoff_splitting.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transformations/wyckoff_splitting`](https://schemas.httk.org/defs/v0.1/properties/transformations/wyckoff_splitting.md)
                
                Wyckoff-position splitting data associated with a subgroup or same-space-group transform.

        * **transport**
            * **[Diffusion coefficient](v0.1/properties/transport/diffusion_coefficient.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transport/diffusion_coefficient`](https://schemas.httk.org/defs/v0.1/properties/transport/diffusion_coefficient.md)
                
                The isotropic self-diffusion coefficient D = tr(D_ij) / 3, in square metre per second (m^2 s^-1).
                Obtained from Green-Kubo or Einstein relations. For example, from the slope of the mean-squared displacement divided by 2d (Einstein), or the time integral of the velocity autocorrelation function (Green-Kubo).
                The species or selection it refers to is recorded alongside.
                A null value means the quantity is not available or not recorded.

            * **[Diffusion running integral](v0.1/properties/transport/diffusion_running_integral.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transport/diffusion_running_integral`](https://schemas.httk.org/defs/v0.1/properties/transport/diffusion_running_integral.md)
                
                Running integral of the velocity autocorrelation tensor, as a function of upper integration limit.

            * **[Diffusion tensor](v0.1/properties/transport/diffusion_tensor.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transport/diffusion_tensor`](https://schemas.httk.org/defs/v0.1/properties/transport/diffusion_tensor.md)
                
                The self-diffusion tensor D_ij, in square metre per second (m^2 s^-1), a 3x3 Cartesian tensor with both indices over `dim_spatial` in the Cartesian frame of the referenced cell.
                Obtained from Green-Kubo or Einstein relations. The tensor is not assumed to be symmetric. The species or selection it refers to is recorded alongside.
                A null value means the quantity is not available or not recorded.

            * **[Mean squared displacement](v0.1/properties/transport/mean_squared_displacement.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transport/mean_squared_displacement`](https://schemas.httk.org/defs/v0.1/properties/transport/mean_squared_displacement.md)
                
                Mean squared displacement tensor as a function of lag time.

            * **[Shear viscosity](v0.1/properties/transport/shear_viscosity.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transport/shear_viscosity`](https://schemas.httk.org/defs/v0.1/properties/transport/shear_viscosity.md)
                
                The shear viscosity, in pascal second (Pa s).
                Obtained from Green-Kubo or Einstein relations. By the Green-Kubo relation eta = V / (kB T) times the time integral of <sigma_xy(0) sigma_xy(t)>, averaged over the independent off-diagonal stress components.
                A null value means the quantity is not available or not recorded.

            * **[Shear viscosity running integral](v0.1/properties/transport/shear_viscosity_running_integral.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transport/shear_viscosity_running_integral`](https://schemas.httk.org/defs/v0.1/properties/transport/shear_viscosity_running_integral.md)
                
                Green-Kubo running integral of the shear stress autocorrelation, as a function of upper integration limit.

            * **[Thermal conductivity](v0.1/properties/transport/thermal_conductivity.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transport/thermal_conductivity`](https://schemas.httk.org/defs/v0.1/properties/transport/thermal_conductivity.md)
                
                The isotropic thermal conductivity, the mean of the diagonal of the thermal conductivity tensor, in watt per metre per kelvin (W m^-1 K^-1).
                Obtained from Green-Kubo or Einstein relations.
                A null value means the quantity is not available or not recorded.

            * **[Thermal conductivity running integral](v0.1/properties/transport/thermal_conductivity_running_integral.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transport/thermal_conductivity_running_integral`](https://schemas.httk.org/defs/v0.1/properties/transport/thermal_conductivity_running_integral.md)
                
                Green-Kubo running integral of the heat-current autocorrelation, as a function of upper integration limit.

            * **[Thermal conductivity tensor](v0.1/properties/transport/thermal_conductivity_tensor.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transport/thermal_conductivity_tensor`](https://schemas.httk.org/defs/v0.1/properties/transport/thermal_conductivity_tensor.md)
                
                The thermal conductivity tensor kappa_ij, in watt per metre per kelvin (W m^-1 K^-1), a 3x3 Cartesian tensor with both indices over `dim_spatial` in the Cartesian frame of the referenced cell.
                Obtained from Green-Kubo or Einstein relations. By the Green-Kubo relation kappa_ij = 1 / (V kB T^2) times the time integral of <J_i(0) J_j(t)>, where J is the extensive heat current. The tensor is not assumed to be symmetric.
                A null value means the quantity is not available or not recorded.

            * **[Velocity autocorrelation](v0.1/properties/transport/velocity_autocorrelation.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/transport/velocity_autocorrelation`](https://schemas.httk.org/defs/v0.1/properties/transport/velocity_autocorrelation.md)
                
                Velocity autocorrelation tensor as a function of lag time.

    * **standards**
        * **[httk definition provider standard](v0.1/standards/httk.md)** (standard) - [`https://schemas.httk.org/defs/v0.1/standards/httk`](https://schemas.httk.org/defs/v0.1/standards/httk.md)
            
            The httk definition provider standard, comprising the spacegroups, pointgroups, and transformations entry types for crystallographic symmetry data.

    * **units**
        * **si**
            * **general**
                * **[femtosecond](v0.1/units/si/general/femtosecond.md)** (unit) - [`https://schemas.httk.org/defs/v0.1/units/si/general/femtosecond`](https://schemas.httk.org/defs/v0.1/units/si/general/femtosecond.md)
                    
                    A unit of time equal to 10^-15 seconds.

                * **[gigapascal](v0.1/units/si/general/gigapascal.md)** (unit) - [`https://schemas.httk.org/defs/v0.1/units/si/general/gigapascal`](https://schemas.httk.org/defs/v0.1/units/si/general/gigapascal.md)
                    
                    A unit of pressure and stress equal to 10^9 pascals.

    * **workflows**
        * **[VASP structure relaxation](v0.1/workflows/vasp-relax.md)** (*[unknown]*) - [`https://schemas.httk.org/defs/v0.1/workflows/vasp-relax`](https://schemas.httk.org/defs/v0.1/workflows/vasp-relax.md)
            
            This workflow declaration defines the httk vasp-relax workflow: it relaxes the geometry of a crystal structure with VASP.
            It defines the meaning of its roles: input role initial_structure is a structures entry containing the structure to relax.
            Output role relaxed_structure is a structures entry containing the relaxed geometry, and output role total_energy is a records entry containing the final total energy of the relaxed structure.

        * **[VASP relaxation and static calculation](v0.1/workflows/vasp-relax-static.md)** (*[unknown]*) - [`https://schemas.httk.org/defs/v0.1/workflows/vasp-relax-static`](https://schemas.httk.org/defs/v0.1/workflows/vasp-relax-static.md)
            
            This workflow declaration defines the httk vasp-relax-static workflow: it relaxes the geometry, then evaluates the relaxed structure with a final static calculation.
            It defines the meaning of its roles: input role initial_structure is a structures entry containing the structure to relax.
            Output role relaxed_structure is a structures entry containing the relaxed geometry, and output role total_energy is a records entry containing the total energy of the relaxed structure from the final static calculation.

        * **[VASP static calculation](v0.1/workflows/vasp-static.md)** (*[unknown]*) - [`https://schemas.httk.org/defs/v0.1/workflows/vasp-static`](https://schemas.httk.org/defs/v0.1/workflows/vasp-static.md)
            
            This workflow declaration defines the httk vasp-static workflow: it performs a single-point total-energy evaluation of a fixed structure with VASP.
            It defines the meaning of its roles: input role initial_structure is a structures entry containing the structure to evaluate.
            Output role total_energy is a records entry containing the total energy of the structure.

