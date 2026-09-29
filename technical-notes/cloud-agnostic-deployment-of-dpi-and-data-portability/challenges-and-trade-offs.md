# Challenges and Trade-offs

Not every DPI deployment requires the same level of cloud-agnostic investment. A small-scale pilot serving a single district has different needs than a national identity system processing millions of transactions daily. The maturity-tiered recommendations in this note help countries "right-size" their approach: start with containerisation and infrastructure-as-code (achievable with modest teams), add data portability measures as user bases grow, and invest in full multi-provider deployment only when the system becomes critical national infrastructure. The key question is not _whether_ to pursue cloud agnosticism, but _how much_ to invest at each stage of system maturity.

That said, cloud-agnostic architecture is not without costs and challenges:

* **Performance Optimisation** — Provider-specific services often offer performance advantages. Cloud-agnostic architecture may sacrifice some optimisation opportunities for portability.
* **Development Velocity** — Abstraction layers add complexity that can slow feature development. Teams must balance portability with delivery speed.
* **Operational Overhead** — Managing portable infrastructure requires expertise across multiple platforms, increasing operational burden compared to deep specialisation in one provider.
* **Cost Considerations** — Cloud-agnostic architecture may increase costs through abstraction overhead, multi-provider testing, or suboptimal resource utilisation. These costs should be weighed against the risks they mitigate.
