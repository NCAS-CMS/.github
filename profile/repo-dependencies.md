# NCAS-CMS Libraries Depedencies Tracker

⚠️ Warning: this dependencies graph is manually created and will not auto-update, so must be
kept in sync.

```mermaid
flowchart LR

    %% ============================================================
    %% CF Data Tools
    %% ============================================================

    cfpython["cf-python"]
    cfdm["cfdm"]
    cfplot["cf-plot"]
    cfunits["cfunits"]

    %% ============================================================
    %% Data Tools
    %% ============================================================

    pyfive["pyfive"]
    pyactivestorage["PyActiveStorage"]
    xnetcdf["xnetcdf"]
    xconv2["xconv2"]
    cmip7_repack["cmip7_repack"]
    umfive["umfive"]
    p5rem["p5rem"]
    h5netcdf["h5netcdf"]

    %% ============================================================
    %% Dependencies
    %% ============================================================

    cfpython --> cfdm
    cfpython --> cfunits
    cfpython --> pyfive

    cfdm --> cfunits
    cfdm --> pyfive

    cfplot --> cfpython

    pyactivestorage --> h5netcdf
    pyactivestorage --> pyfive

    xnetcdf --> pyfive
    xnetcdf --> umfive

    xconv2 --> cfpython
    xconv2 --> cfdm
    xconv2 --> cfplot
    xconv2 --> p5rem
    xconv2 --> pyfive

    cmip7_repack --> pyfive

    umfive --> pyfive

    p5rem --> pyfive
    p5rem --> pyactivestorage

    %% ============================================================
    %% Category colours
    %% ============================================================

    classDef cf fill:#DCE6F1,stroke:#4472C4,color:#000
    classDef data fill:#E2EFDA,stroke:#70AD47,color:#000

    class cfpython,cfdm,cfplot,cfunits cf
    class pyfive,pyactivestorage,xnetcdf,xconv2,cmip7_repack,umfive,p5rem,h5netcdf data

    %% ============================================================
    %% Visible legend
    %% ============================================================

    subgraph LEGEND["Legend"]
        direction TB

        legend_cf["CF Data Tools"]
        legend_data["Data Tools"]

        class legend_cf cf
        class legend_data data
    end

    %% Styling
    classDef cf fill:#DCE6F1,stroke:#4472C4,color:#000
    classDef data fill:#E2EFDA,stroke:#70AD47,color:#000
    classDef training fill:#FFF2CC,stroke:#BF9000,color:#000
    classDef docs fill:#E7E6E6,stroke:#7F7F7F,color:#000
    classDef website fill:#FCE4D6,stroke:#C55A11,color:#000
    classDef deprecated fill:#EDEDED,stroke:#A6A6A6,color:#666

    class cfpython,cfdm,cfplot,cfunits cf
    class pyfive,pyactivestorage,xnetcdf,xconv2,cmip7_repack,umfive,p5rem,h5netcdf data
```
