import { useState, useEffect, useRef } from "react";

// ============================================================
// MOCK PROPERTY DATABASE
// ============================================================
const PROPERTIES = [
  {
    id: "P001",
    address: "2847 SW 22nd Terrace",
    city: "Miami",
    zipCode: "33133",
    neighborhood: "Coconut Grove",
    propertyType: "Single Family",
    price: 895000,
    beds: 4,
    baths: 3,
    livingArea: 2100,
    lotSize: 7500,
    yearBuilt: 1978,
    hoa: 0,
    taxes: 9200,
    insuranceEstimate: 4800,
    estimatedRent: 5800,
    currentUse: "Owner Occupied",
    zoningCode: "RS-1",
    folio: "01-4122-000-0120",
    lastSalePrice: 620000,
    lastSaleDate: "2019-03-14",
    assessedValue: 780000,
    notes: "Corner lot, older home with good bones. Large lot for area.",
    tags: ["Value-Add", "Corner Lot", "Grove"],
    color: "#1a6b4a"
  },
  {
    id: "P002",
    address: "1401 Brickell Bay Dr #2204",
    city: "Miami",
    zipCode: "33131",
    neighborhood: "Brickell",
    propertyType: "Condo",
    price: 1250000,
    beds: 2,
    baths: 2,
    livingArea: 1320,
    lotSize: 0,
    yearBuilt: 2008,
    hoa: 1850,
    taxes: 13500,
    insuranceEstimate: 3200,
    estimatedRent: 7500,
    currentUse: "Rental",
    zoningCode: "SD-2",
    folio: "01-4139-082-2204",
    lastSalePrice: 980000,
    lastSaleDate: "2021-07-22",
    assessedValue: 1100000,
    notes: "Bay views, luxury building. Strong STR demand. No STR restriction in building.",
    tags: ["Best ROI", "STR-Friendly", "Brickell"],
    color: "#1a4a6b"
  },
  {
    id: "P003",
    address: "5812 NE 4th Avenue",
    city: "Miami",
    zipCode: "33137",
    neighborhood: "Little Haiti / MiMo District",
    propertyType: "Duplex",
    price: 680000,
    beds: 5,
    baths: 3,
    livingArea: 2400,
    lotSize: 6250,
    yearBuilt: 1963,
    hoa: 0,
    taxes: 7100,
    insuranceEstimate: 4200,
    estimatedRent: 6200,
    currentUse: "Tenant Occupied",
    zoningCode: "T4-R",
    folio: "01-3214-009-0380",
    lastSalePrice: 410000,
    lastSaleDate: "2018-11-05",
    assessedValue: 595000,
    notes: "Both units currently rented. T4-R zoning may allow additional density. Emerging corridor.",
    tags: ["Best Cash Flow", "Duplex", "Value-Add"],
    color: "#6b3a1a"
  },
  {
    id: "P004",
    address: "430 NW 28th Street",
    city: "Miami",
    zipCode: "33127",
    neighborhood: "Wynwood",
    propertyType: "Vacant Lot",
    price: 1100000,
    beds: 0,
    baths: 0,
    livingArea: 0,
    lotSize: 10500,
    yearBuilt: null,
    hoa: 0,
    taxes: 11000,
    insuranceEstimate: 1200,
    estimatedRent: 0,
    currentUse: "Vacant",
    zoningCode: "T5-O",
    folio: "01-3125-018-0550",
    lastSalePrice: 600000,
    lastSaleDate: "2020-04-30",
    assessedValue: 920000,
    notes: "T5-O zoning. Active Wynwood arts corridor. High development upside. Adjacent parcels being assembled.",
    tags: ["Development Play", "Wynwood", "T5 Zoning"],
    color: "#5a1a6b"
  },
  {
    id: "P005",
    address: "1220 Coral Way",
    city: "Miami",
    zipCode: "33145",
    neighborhood: "Coral Way",
    propertyType: "Townhouse",
    price: 725000,
    beds: 3,
    baths: 2.5,
    livingArea: 1850,
    lotSize: 2200,
    yearBuilt: 2016,
    hoa: 320,
    taxes: 7800,
    insuranceEstimate: 3600,
    estimatedRent: 4400,
    currentUse: "Owner Occupied",
    zoningCode: "T3-O",
    folio: "01-4108-044-0270",
    lastSalePrice: 590000,
    lastSaleDate: "2020-09-18",
    assessedValue: 660000,
    notes: "Modern construction, low maintenance. Good schools nearby. Miami corridor appreciation trend.",
    tags: ["Best Fit", "Family-Friendly", "Low Risk"],
    color: "#1a5c6b"
  },
  {
    id: "P006",
    address: "7801 Biscayne Blvd",
    city: "Miami",
    zipCode: "33138",
    neighborhood: "Upper East Side",
    propertyType: "Mixed Use",
    price: 2200000,
    beds: 6,
    baths: 4,
    livingArea: 4800,
    lotSize: 14000,
    yearBuilt: 1951,
    hoa: 0,
    taxes: 22000,
    insuranceEstimate: 9800,
    estimatedRent: 14500,
    currentUse: "Mixed Retail/Residential",
    zoningCode: "T6-8",
    folio: "01-3207-001-0120",
    lastSalePrice: 1400000,
    lastSaleDate: "2017-02-14",
    assessedValue: 1850000,
    notes: "Large T6 lot. Potential to build 8-story mixed use. Strong corridor improvement. Rare opportunity.",
    tags: ["Redevelopment", "T6 Zoning", "Rare"],
    color: "#6b1a2a"
  }
];

// ============================================================
// SCORING ENGINE
// ============================================================
function scoreProperty(property, profile) {
  let budgetScore = 0;
  let locationScore = 0;
  let featureScore = 0;
  let investmentScore = 0;
  let developmentScore = 0;
  const reasons = [];

  // Budget (25%)
  const priceFit = property.price <= profile.budget * 1.1;
  const monthlyPI = calcMortgagePI(property.price * (1 - (profile.downPayment || 20) / 100), 7.25, 30);
  const totalMonthly = monthlyPI + property.taxes / 12 + property.insuranceEstimate / 12 + property.hoa;
  const paymentFit = totalMonthly <= (profile.monthlyPaymentTarget || 99999) * 1.15;

  if (priceFit && paymentFit) { budgetScore = 100; reasons.push("Fits your budget and monthly target"); }
  else if (priceFit) { budgetScore = 75; reasons.push("Within purchase budget"); }
  else if (property.price <= profile.budget * 1.2) { budgetScore = 40; }
  else { budgetScore = 10; }

  // Location (20%)
  const preferred = profile.preferredAreas || [];
  const avoided = profile.avoidedAreas || [];
  if (avoided.some(a => property.neighborhood.toLowerCase().includes(a.toLowerCase()))) {
    locationScore = 0;
  } else if (preferred.length === 0 || preferred.some(a => property.neighborhood.toLowerCase().includes(a.toLowerCase()))) {
    locationScore = 90;
    if (preferred.some(a => property.neighborhood.toLowerCase().includes(a.toLowerCase()))) reasons.push("In your preferred area");
  } else {
    locationScore = 50;
  }

  // Features (15%)
  const bedMatch = !profile.beds || property.beds >= parseInt(profile.beds || 0);
  const typeMatch = !profile.propertyType || profile.propertyType === "Any" || property.propertyType.toLowerCase().includes(profile.propertyType.toLowerCase());
  if (bedMatch && typeMatch) { featureScore = 95; }
  else if (bedMatch || typeMatch) { featureScore = 60; }
  else { featureScore = 25; }

  // Investment (20%)
  if (profile.userType === "investor" || profile.userType === "developer") {
    const rentYield = property.estimatedRent > 0 ? (property.estimatedRent * 12 / property.price) * 100 : 0;
    if (rentYield >= 7) { investmentScore = 100; reasons.push("Strong rental yield above 7%"); }
    else if (rentYield >= 5) { investmentScore = 75; reasons.push("Solid rental income potential"); }
    else if (rentYield >= 3) { investmentScore = 50; }
    else { investmentScore = 20; }
  } else {
    investmentScore = 60;
  }

  // Development (20%)
  const devZones = ["T4", "T5", "T6", "SD", "duplex", "multifamily"];
  const hasDevPotential = devZones.some(z => property.zoningCode.toUpperCase().includes(z.toUpperCase()) || property.propertyType.toLowerCase().includes(z.toLowerCase()));
  const bigLot = property.lotSize >= 6000;
  if (profile.developmentInterest === "high" || profile.userType === "developer") {
    if (hasDevPotential && bigLot) { developmentScore = 100; reasons.push("Strong development upside—large lot + flexible zoning"); }
    else if (hasDevPotential || bigLot) { developmentScore = 65; reasons.push("Possible development potential—needs verification"); }
    else { developmentScore = 20; }
  } else {
    developmentScore = hasDevPotential ? 70 : 50;
  }

  const totalScore = Math.round(
    budgetScore * 0.25 + locationScore * 0.20 + featureScore * 0.15 + investmentScore * 0.20 + developmentScore * 0.20
  );

  return { budgetScore, locationScore, featureScore, investmentScore, developmentScore, totalScore, reasons };
}

// ============================================================
// FINANCIAL ENGINE
// ============================================================
function calcMortgagePI(principal, annualRate, years) {
  const r = annualRate / 100 / 12;
  const n = years * 12;
  return Math.round(principal * (r * Math.pow(1 + r, n)) / (Math.pow(1 + r, n) - 1));
}

function analyzeFinancials(property, profile, scenario = "base") {
  const downPct = (profile.downPayment || 20) / 100;
  const multiplier = scenario === "conservative" ? 0.88 : scenario === "aggressive" ? 1.12 : 1.0;
  const rateAdj = scenario === "conservative" ? 0.5 : scenario === "aggressive" ? -0.25 : 0;

  const loanAmount = property.price * (1 - downPct);
  const rate = 7.25 + rateAdj;
  const mortgagePI = calcMortgagePI(loanAmount, rate, 30);
  const taxesMonthly = Math.round(property.taxes / 12);
  const insuranceMonthly = Math.round(property.insuranceEstimate / 12);
  const hoaMonthly = property.hoa;
  const maintenanceReserve = Math.round(property.price * 0.01 / 12);
  const vacancyReserve = property.estimatedRent > 0 ? Math.round(property.estimatedRent * 0.08) : 0;
  const managementReserve = property.estimatedRent > 0 ? Math.round(property.estimatedRent * 0.10) : 0;

  const totalMonthlyCost = mortgagePI + taxesMonthly + insuranceMonthly + hoaMonthly + maintenanceReserve;
  const monthlyRent = Math.round(property.estimatedRent * multiplier);
  const grossIncome = monthlyRent * 12;
  const operatingExpenses = (taxesMonthly + insuranceMonthly + hoaMonthly + maintenanceReserve + vacancyReserve + managementReserve) * 12;
  const noi = grossIncome - operatingExpenses;
  const annualDebt = mortgagePI * 12;
  const annualCashFlow = noi - annualDebt;
  const downPaymentAmt = property.price * downPct;
  const cashOnCash = downPaymentAmt > 0 ? ((annualCashFlow / downPaymentAmt) * 100).toFixed(1) : "N/A";
  const capRate = property.price > 0 && noi > 0 ? ((noi / property.price) * 100).toFixed(2) : "N/A";
  const roi = downPaymentAmt > 0 ? (((annualCashFlow + property.price * 0.04) / downPaymentAmt) * 100).toFixed(1) : "N/A";

  return {
    loanAmount: Math.round(loanAmount),
    rate,
    mortgagePI,
    taxesMonthly,
    insuranceMonthly,
    hoaMonthly,
    maintenanceReserve,
    vacancyReserve,
    managementReserve,
    totalMonthlyCost,
    monthlyRent,
    grossIncome,
    operatingExpenses,
    noi: Math.round(noi),
    annualCashFlow: Math.round(annualCashFlow),
    cashOnCash,
    capRate,
    roi,
    downPaymentAmt: Math.round(downPaymentAmt),
    scenario
  };
}

// ============================================================
// ZONING ENGINE
// ============================================================
function analyzeZoning(property) {
  const z = property.zoningCode;
  const lot = property.lotSize;
  let maxUnits = 1, aduPotential = false, duplexPotential = false, multifamilyPotential = false, redevelopmentPotential = false;
  let densityClue = "Single-family residential";
  let confidence = "medium";
  let explanation = "";

  if (z.startsWith("T6") || z.includes("SD-2")) {
    maxUnits = lot > 10000 ? 20 : 8;
    multifamilyPotential = true;
    redevelopmentPotential = true;
    densityClue = "High-density mixed-use or multifamily";
    confidence = "high";
    explanation = `${z} zoning generally permits high-density development. Lot size of ${lot > 0 ? lot.toLocaleString() : "N/A"} sq ft may support significant unit count. Height allowances and FAR require municipal verification.`;
  } else if (z.startsWith("T5")) {
    maxUnits = lot > 8000 ? 12 : 6;
    multifamilyPotential = true;
    redevelopmentPotential = true;
    duplexPotential = true;
    densityClue = "Urban center—5-story possible";
    confidence = "high";
    explanation = `T5 zoning (Urban Center) in Miami's Transect system allows mid-rise multifamily. This lot may support 6–12 units depending on exact dimensions, setbacks, and parking requirements.`;
  } else if (z.startsWith("T4")) {
    maxUnits = 4;
    duplexPotential = true;
    aduPotential = true;
    densityClue = "General urban—duplex to fourplex range";
    confidence = "medium";
    explanation = `T4 zoning (General Urban) typically permits duplexes and potentially small multifamily. An ADU may also be possible. Exact allowances depend on lot dimensions and local variances.`;
  } else if (z.startsWith("T3")) {
    maxUnits = 2;
    aduPotential = lot >= 5000;
    densityClue = "Sub-urban—primarily single-family, possible ADU";
    confidence = "medium";
    explanation = `T3 (Sub-Urban) is primarily single-family. ADU potential if lot exceeds 5,000 sq ft—which ${lot >= 5000 ? "this lot does" : "this lot may not"}. Verification with City of Miami required.`;
  } else if (z.startsWith("RS")) {
    maxUnits = 1;
    aduPotential = lot >= 7500;
    densityClue = "Single-family only (RS zoning)";
    confidence = "high";
    explanation = `RS zoning is strictly residential single-family. No duplex or multifamily is typically permitted. ${lot >= 7500 ? "The larger lot may allow an accessory dwelling unit (ADU)—verify with Miami-Dade." : "Lot size limits additional unit potential."}`;
  } else {
    densityClue = "Custom / mixed-use zoning";
    confidence = "low";
    explanation = `Zoning code ${z} requires direct lookup in the Miami-Dade property portal and Gridics zoning map for accurate development parameters.`;
  }

  return {
    zoningCode: z,
    lotSize: lot,
    maxUnitsEstimated: maxUnits,
    aduPotential,
    duplexPotential,
    multifamilyPotential,
    redevelopmentPotential,
    densityClue,
    confidenceLevel: confidence,
    explanation,
    warnings: [
      "All zoning analysis is preliminary and must be verified with the City of Miami or Miami-Dade County.",
      "Actual unit count depends on setbacks, FAR, parking, and current code amendments.",
      "This analysis does not constitute legal or planning advice."
    ],
    sources: ["Miami-Dade Property Search", "City of Miami Miami 21 Code", "Gridics Zoning Map"]
  };
}

// ============================================================
// COLOR & UTILITY HELPERS
// ============================================================
const fmt = (n) => n != null ? `$${Math.round(n).toLocaleString()}` : "N/A";
const pct = (n) => n != null ? `${n}%` : "N/A";
const scoreColor = (s) => s >= 80 ? "#16a34a" : s >= 60 ? "#d97706" : "#dc2626";
const tagColors = {
  "Best Fit": { bg: "#dbeafe", text: "#1e40af" },
  "Best ROI": { bg: "#d1fae5", text: "#065f46" },
  "Best Cash Flow": { bg: "#d1fae5", text: "#065f46" },
  "Value-Add": { bg: "#fef3c7", text: "#92400e" },
  "Development Play": { bg: "#ede9fe", text: "#4c1d95" },
  "Redevelopment": { bg: "#ede9fe", text: "#4c1d95" },
  "Low Risk": { bg: "#e0f2fe", text: "#075985" },
  "STR-Friendly": { bg: "#fce7f3", text: "#9d174d" },
  "Family-Friendly": { bg: "#e0f2fe", text: "#075985" },
};

// ============================================================
// COMPONENTS
// ============================================================

const Tag = ({ label }) => {
  const style = tagColors[label] || { bg: "#f3f4f6", text: "#374151" };
  return (
    <span style={{ background: style.bg, color: style.text, fontSize: 11, fontWeight: 600, padding: "2px 8px", borderRadius: 99, letterSpacing: "0.3px" }}>
      {label}
    </span>
  );
};

const ScoreBar = ({ label, value, max = 100 }) => (
  <div style={{ marginBottom: 8 }}>
    <div style={{ display: "flex", justifyContent: "space-between", fontSize: 12, marginBottom: 3 }}>
      <span style={{ color: "#6b7280" }}>{label}</span>
      <span style={{ fontWeight: 600, color: scoreColor(value) }}>{value}</span>
    </div>
    <div style={{ background: "#f3f4f6", borderRadius: 99, height: 5 }}>
      <div style={{ width: `${(value / max) * 100}%`, height: 5, borderRadius: 99, background: scoreColor(value), transition: "width 0.6s ease" }} />
    </div>
  </div>
);

const Stat = ({ label, value, sub, highlight }) => (
  <div style={{ background: highlight ? "#f0fdf4" : "#f9fafb", borderRadius: 10, padding: "10px 14px", border: highlight ? "1px solid #bbf7d0" : "1px solid #e5e7eb" }}>
    <div style={{ fontSize: 11, color: "#6b7280", marginBottom: 3, textTransform: "uppercase", letterSpacing: "0.5px" }}>{label}</div>
    <div style={{ fontSize: 18, fontWeight: 700, color: highlight ? "#15803d" : "#111827" }}>{value}</div>
    {sub && <div style={{ fontSize: 11, color: "#9ca3af", marginTop: 2 }}>{sub}</div>}
  </div>
);

// ============================================================
// PAGES
// ============================================================

// --- LANDING PAGE ---
const LandingPage = ({ onStart, onAnalyze, onZoning }) => (
  <div style={{ minHeight: "100vh", background: "linear-gradient(135deg, #0f172a 0%, #1e293b 50%, #0f2027 100%)", fontFamily: "'Georgia', serif" }}>
    {/* Nav */}
    <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", padding: "20px 40px", borderBottom: "1px solid rgba(255,255,255,0.08)" }}>
      <div style={{ display: "flex", alignItems: "center", gap: 10 }}>
        <div style={{ width: 32, height: 32, background: "linear-gradient(135deg, #10b981, #3b82f6)", borderRadius: 8 }} />
        <span style={{ color: "#f1f5f9", fontSize: 18, fontWeight: 700, letterSpacing: "-0.5px", fontFamily: "sans-serif" }}>MiamiIntel</span>
      </div>
      <div style={{ display: "flex", gap: 24, fontSize: 14, color: "#94a3b8", fontFamily: "sans-serif" }}>
        <span style={{ cursor: "pointer", transition: "color 0.2s" }} onMouseOver={e => e.target.style.color = "#f1f5f9"} onMouseOut={e => e.target.style.color = "#94a3b8"}>Market</span>
        <span style={{ cursor: "pointer", transition: "color 0.2s" }} onMouseOver={e => e.target.style.color = "#f1f5f9"} onMouseOut={e => e.target.style.color = "#94a3b8"}>Analysis</span>
        <span style={{ cursor: "pointer", transition: "color 0.2s" }} onMouseOver={e => e.target.style.color = "#f1f5f9"} onMouseOut={e => e.target.style.color = "#94a3b8"}>Team</span>
      </div>
    </div>

    {/* Hero */}
    <div style={{ maxWidth: 960, margin: "0 auto", padding: "80px 40px 60px", textAlign: "center" }}>
      <div style={{ display: "inline-block", background: "rgba(16,185,129,0.15)", border: "1px solid rgba(16,185,129,0.3)", borderRadius: 99, padding: "6px 16px", fontSize: 12, color: "#34d399", marginBottom: 32, fontFamily: "sans-serif", letterSpacing: "0.5px" }}>
        MIAMI REAL ESTATE INTELLIGENCE PLATFORM
      </div>
      <h1 style={{ fontSize: "clamp(36px, 6vw, 68px)", fontWeight: 700, color: "#f8fafc", lineHeight: 1.1, marginBottom: 24, letterSpacing: "-2px" }}>
        Find the right property<br />
        <span style={{ background: "linear-gradient(90deg, #10b981, #3b82f6)", WebkitBackgroundClip: "text", WebkitTextFillColor: "transparent" }}>with AI intelligence</span>
      </h1>
      <p style={{ fontSize: 20, color: "#94a3b8", maxWidth: 600, margin: "0 auto 48px", lineHeight: 1.7, fontFamily: "sans-serif", fontWeight: 400 }}>
        Not just listings. We help you understand <em>what to buy</em>, <em>why it fits</em>, and what financial and development upside it may carry.
      </p>

      {/* CTAs */}
      <div style={{ display: "flex", gap: 16, justifyContent: "center", flexWrap: "wrap", marginBottom: 64 }}>
        <button onClick={onStart} style={{ background: "linear-gradient(135deg, #10b981, #059669)", color: "white", border: "none", borderRadius: 12, padding: "16px 32px", fontSize: 16, fontWeight: 600, cursor: "pointer", fontFamily: "sans-serif", boxShadow: "0 4px 24px rgba(16,185,129,0.4)" }}>
          Start AI Search →
        </button>
        <button onClick={onAnalyze} style={{ background: "rgba(59,130,246,0.15)", color: "#93c5fd", border: "1px solid rgba(59,130,246,0.3)", borderRadius: 12, padding: "16px 32px", fontSize: 16, fontWeight: 600, cursor: "pointer", fontFamily: "sans-serif" }}>
          Analyze a Property
        </button>
        <button onClick={onZoning} style={{ background: "rgba(139,92,246,0.15)", color: "#c4b5fd", border: "1px solid rgba(139,92,246,0.3)", borderRadius: 12, padding: "16px 32px", fontSize: 16, fontWeight: 600, cursor: "pointer", fontFamily: "sans-serif" }}>
          Check Zoning Potential
        </button>
      </div>

      {/* Feature Grid */}
      <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit, minmax(240px, 1fr))", gap: 20, textAlign: "left" }}>
        {[
          { icon: "🏠", title: "AI Property Matching", desc: "Scored against your exact budget, lifestyle, and goals. Not just keyword filters." },
          { icon: "📊", title: "Financial Analysis", desc: "Mortgage, NOI, cash-on-cash, cap rate. Conservative, base, and aggressive scenarios." },
          { icon: "🗺️", title: "Zoning Intelligence", desc: "Duplex, ADU, multifamily, and redevelopment clues based on Miami-21 zoning codes." },
          { icon: "🤝", title: "Human Advisor Bridge", desc: "AI handles discovery. Our licensed team handles negotiations, contracts, and closing." },
        ].map(f => (
          <div key={f.title} style={{ background: "rgba(255,255,255,0.04)", border: "1px solid rgba(255,255,255,0.08)", borderRadius: 16, padding: "24px 20px" }}>
            <div style={{ fontSize: 28, marginBottom: 12 }}>{f.icon}</div>
            <div style={{ fontSize: 15, fontWeight: 600, color: "#f1f5f9", marginBottom: 8, fontFamily: "sans-serif" }}>{f.title}</div>
            <div style={{ fontSize: 14, color: "#64748b", lineHeight: 1.6, fontFamily: "sans-serif" }}>{f.desc}</div>
          </div>
        ))}
      </div>
    </div>
  </div>
);

// --- AI INTAKE ---
const INTAKE_QUESTIONS = [
  { id: "userType", question: "What's your primary goal?", type: "choice", choices: [{ value: "homebuyer", label: "Buy a home to live in" }, { value: "investor", label: "Investment & rental income" }, { value: "developer", label: "Development / value-add" }] },
  { id: "budget", question: "What's your maximum purchase budget?", type: "choice", choices: [{ value: 500000, label: "Up to $500K" }, { value: 750000, label: "Up to $750K" }, { value: 1000000, label: "Up to $1M" }, { value: 2000000, label: "Up to $2M" }, { value: 5000000, label: "$2M+" }] },
  { id: "downPayment", question: "Down payment you're working with?", type: "choice", choices: [{ value: 5, label: "5% (FHA / low down)" }, { value: 10, label: "10%" }, { value: 20, label: "20% (conventional)" }, { value: 25, label: "25%+" }] },
  { id: "monthlyPaymentTarget", question: "Max comfortable monthly payment (PITI)?", type: "choice", choices: [{ value: 3500, label: "Under $3,500" }, { value: 5000, label: "Under $5,000" }, { value: 8000, label: "Under $8,000" }, { value: 15000, label: "Under $15,000" }, { value: 99999, label: "Not a constraint" }] },
  { id: "preferredAreas", question: "Preferred neighborhoods? (pick all that apply)", type: "multi", choices: [{ value: "Brickell", label: "Brickell" }, { value: "Coconut Grove", label: "Coconut Grove" }, { value: "Wynwood", label: "Wynwood" }, { value: "Coral Way", label: "Coral Way" }, { value: "Upper East Side", label: "Upper East Side" }, { value: "Little Haiti", label: "Little Haiti / MiMo" }] },
  { id: "propertyType", question: "Property type preference?", type: "choice", choices: [{ value: "Any", label: "No preference" }, { value: "Single Family", label: "Single Family" }, { value: "Condo", label: "Condo" }, { value: "Duplex", label: "Duplex / Multifamily" }, { value: "Vacant Lot", label: "Land / Lot" }, { value: "Townhouse", label: "Townhouse" }] },
  { id: "beds", question: "Minimum bedrooms?", type: "choice", choices: [{ value: 0, label: "No minimum" }, { value: 2, label: "2+ beds" }, { value: 3, label: "3+ beds" }, { value: 4, label: "4+ beds" }] },
  { id: "riskTolerance", question: "Risk tolerance?", type: "choice", choices: [{ value: "low", label: "Low — stable, proven assets" }, { value: "medium", label: "Medium — some upside risk is fine" }, { value: "high", label: "High — max upside, accept more risk" }] },
  { id: "developmentInterest", question: "Interest in development / adding units?", type: "choice", choices: [{ value: "none", label: "Not interested" }, { value: "low", label: "Nice to have" }, { value: "high", label: "Major priority" }] },
  { id: "timeline", question: "Timeline to purchase?", type: "choice", choices: [{ value: "asap", label: "As soon as possible" }, { value: "3months", label: "1–3 months" }, { value: "6months", label: "3–6 months" }, { value: "exploring", label: "Just exploring" }] },
];

const IntakePage = ({ onComplete }) => {
  const [step, setStep] = useState(0);
  const [profile, setProfile] = useState({});
  const [selected, setSelected] = useState(null);
  const [multiSelected, setMultiSelected] = useState([]);
  const q = INTAKE_QUESTIONS[step];
  const isLast = step === INTAKE_QUESTIONS.length - 1;

  const handleNext = () => {
    const val = q.type === "multi" ? multiSelected : selected;
    const newProfile = { ...profile, [q.id]: val };
    setProfile(newProfile);
    if (isLast) { onComplete(newProfile); }
    else { setStep(s => s + 1); setSelected(null); setMultiSelected([]); }
  };

  const toggleMulti = (val) => setMultiSelected(prev => prev.includes(val) ? prev.filter(v => v !== val) : [...prev, val]);

  const progressPct = ((step) / INTAKE_QUESTIONS.length) * 100;

  return (
    <div style={{ minHeight: "100vh", background: "#0f172a", display: "flex", alignItems: "center", justifyContent: "center", padding: 24, fontFamily: "sans-serif" }}>
      <div style={{ maxWidth: 560, width: "100%" }}>
        {/* Progress */}
        <div style={{ marginBottom: 32 }}>
          <div style={{ display: "flex", justifyContent: "space-between", fontSize: 13, color: "#64748b", marginBottom: 8 }}>
            <span>Step {step + 1} of {INTAKE_QUESTIONS.length}</span>
            <span>{Math.round(progressPct)}% complete</span>
          </div>
          <div style={{ background: "#1e293b", borderRadius: 99, height: 4 }}>
            <div style={{ width: `${progressPct}%`, height: 4, background: "linear-gradient(90deg, #10b981, #3b82f6)", borderRadius: 99, transition: "width 0.4s ease" }} />
          </div>
        </div>

        <div style={{ background: "#1e293b", border: "1px solid #334155", borderRadius: 20, padding: 40 }}>
          <div style={{ fontSize: 13, color: "#10b981", marginBottom: 12, letterSpacing: "0.5px", textTransform: "uppercase" }}>AI Intake</div>
          <h2 style={{ fontSize: 24, color: "#f1f5f9", fontWeight: 600, marginBottom: 32, lineHeight: 1.3, fontFamily: "Georgia, serif" }}>{q.question}</h2>

          <div style={{ display: "flex", flexDirection: "column", gap: 10, marginBottom: 32 }}>
            {q.choices.map(c => {
              const isActive = q.type === "multi" ? multiSelected.includes(c.value) : selected === c.value;
              return (
                <button key={String(c.value)} onClick={() => q.type === "multi" ? toggleMulti(c.value) : setSelected(c.value)}
                  style={{ background: isActive ? "rgba(16,185,129,0.15)" : "rgba(255,255,255,0.03)", border: isActive ? "1px solid #10b981" : "1px solid #334155", borderRadius: 12, padding: "14px 20px", color: isActive ? "#34d399" : "#94a3b8", fontSize: 15, cursor: "pointer", textAlign: "left", transition: "all 0.15s", fontFamily: "sans-serif" }}>
                  {isActive ? "✓ " : ""}{c.label}
                </button>
              );
            })}
          </div>

          <button onClick={handleNext} disabled={q.type === "multi" ? multiSelected.length === 0 : !selected}
            style={{ width: "100%", background: (q.type === "multi" ? multiSelected.length > 0 : selected) ? "linear-gradient(135deg, #10b981, #059669)" : "#1e293b", color: (q.type === "multi" ? multiSelected.length > 0 : selected) ? "white" : "#475569", border: "none", borderRadius: 12, padding: "16px", fontSize: 16, fontWeight: 600, cursor: (q.type === "multi" ? multiSelected.length > 0 : selected) ? "pointer" : "not-allowed", transition: "all 0.2s" }}>
            {isLast ? "Find My Properties →" : "Next →"}
          </button>
        </div>
      </div>
    </div>
  );
};

// --- RESULTS PAGE ---
const ResultsPage = ({ profile, onSelect, onCompare }) => {
  const [compareList, setCompareList] = useState([]);
  const scored = PROPERTIES.map(p => ({ ...p, score: scoreProperty(p, profile) }))
    .filter(p => p.price <= (profile.budget || 99999999) * 1.25)
    .sort((a, b) => b.score.totalScore - a.score.totalScore)
    .slice(0, 5);

  const toggleCompare = (id) => {
    setCompareList(prev => prev.includes(id) ? prev.filter(x => x !== id) : prev.length < 4 ? [...prev, id] : prev);
  };

  return (
    <div style={{ minHeight: "100vh", background: "#f8fafc", fontFamily: "sans-serif" }}>
      <div style={{ background: "#0f172a", padding: "24px 40px", display: "flex", justifyContent: "space-between", alignItems: "center" }}>
        <div>
          <div style={{ fontSize: 13, color: "#10b981", marginBottom: 4 }}>AI MATCH RESULTS</div>
          <div style={{ fontSize: 22, color: "#f1f5f9", fontWeight: 600, fontFamily: "Georgia, serif" }}>Top {scored.length} Properties for You</div>
        </div>
        {compareList.length >= 2 && (
          <button onClick={() => onCompare(compareList.map(id => scored.find(p => p.id === id)))}
            style={{ background: "#3b82f6", color: "white", border: "none", borderRadius: 10, padding: "12px 24px", fontSize: 14, fontWeight: 600, cursor: "pointer" }}>
            Compare {compareList.length} Properties
          </button>
        )}
      </div>

      <div style={{ maxWidth: 1100, margin: "0 auto", padding: "32px 24px" }}>
        <div style={{ background: "#e0f2fe", border: "1px solid #bae6fd", borderRadius: 12, padding: "14px 20px", marginBottom: 28, fontSize: 14, color: "#0369a1" }}>
          <strong>Profile Summary:</strong> {profile.userType === "homebuyer" ? "Primary Home Buyer" : profile.userType === "investor" ? "Real Estate Investor" : "Developer / Value-Add"} · Budget {fmt(profile.budget)} · Down {profile.downPayment}% · {(profile.preferredAreas || []).join(", ") || "Miami-wide"}
        </div>

        <div style={{ display: "flex", flexDirection: "column", gap: 20 }}>
          {scored.map((p, i) => {
            const fin = analyzeFinancials(p, profile);
            const isComparing = compareList.includes(p.id);
            return (
              <div key={p.id} style={{ background: "white", borderRadius: 16, border: isComparing ? "2px solid #3b82f6" : "1px solid #e5e7eb", boxShadow: "0 2px 12px rgba(0,0,0,0.06)", overflow: "hidden" }}>
                <div style={{ display: "grid", gridTemplateColumns: "260px 1fr", minHeight: 200 }}>
                  {/* Left: image placeholder */}
                  <div style={{ background: `linear-gradient(135deg, ${p.color}cc, ${p.color}44)`, display: "flex", flexDirection: "column", alignItems: "center", justifyContent: "center", position: "relative", padding: 20 }}>
                    {i === 0 && <div style={{ position: "absolute", top: 12, left: 12, background: "#10b981", color: "white", fontSize: 11, fontWeight: 700, borderRadius: 99, padding: "4px 10px" }}>BEST MATCH</div>}
                    <div style={{ fontSize: 40, marginBottom: 8 }}>{p.propertyType === "Vacant Lot" ? "🏗️" : p.propertyType === "Condo" ? "🏢" : p.propertyType === "Duplex" ? "🏘️" : p.propertyType === "Mixed Use" ? "🏙️" : "🏡"}</div>
                    <div style={{ fontSize: 26, fontWeight: 700, color: "white" }}>{fmt(p.price)}</div>
                    <div style={{ fontSize: 13, color: "rgba(255,255,255,0.8)", marginTop: 4 }}>{p.neighborhood}</div>
                    <div style={{ marginTop: 12, display: "flex", flexWrap: "wrap", gap: 4, justifyContent: "center" }}>
                      {p.tags.map(t => <Tag key={t} label={t} />)}
                    </div>
                  </div>

                  {/* Right: details */}
                  <div style={{ padding: "20px 24px" }}>
                    <div style={{ display: "flex", justifyContent: "space-between", alignItems: "flex-start", marginBottom: 12 }}>
                      <div>
                        <div style={{ fontSize: 16, fontWeight: 700, color: "#111827" }}>{p.address}</div>
                        <div style={{ fontSize: 13, color: "#6b7280" }}>{p.city}, FL {p.zipCode} · {p.propertyType} · Zoning: {p.zoningCode}</div>
                      </div>
                      <div style={{ textAlign: "right" }}>
                        <div style={{ fontSize: 28, fontWeight: 800, color: scoreColor(p.score.totalScore) }}>{p.score.totalScore}</div>
                        <div style={{ fontSize: 11, color: "#9ca3af" }}>Match Score</div>
                      </div>
                    </div>

                    <div style={{ display: "grid", gridTemplateColumns: "repeat(5, 1fr)", gap: 10, marginBottom: 14 }}>
                      {p.beds > 0 && <Stat label="Beds" value={p.beds} />}
                      {p.baths > 0 && <Stat label="Baths" value={p.baths} />}
                      {p.livingArea > 0 && <Stat label="Sq Ft" value={p.livingArea.toLocaleString()} />}
                      {p.lotSize > 0 && <Stat label="Lot" value={`${p.lotSize.toLocaleString()} sf`} />}
                      <Stat label="Est Rent" value={p.estimatedRent > 0 ? fmt(p.estimatedRent) + "/mo" : "N/A"} />
                    </div>

                    <div style={{ display: "grid", gridTemplateColumns: "repeat(3, 1fr)", gap: 10, marginBottom: 14 }}>
                      <Stat label="Monthly PITI" value={fmt(fin.totalMonthlyCost)} />
                      <Stat label="NOI (est.)" value={fin.noi > 0 ? fmt(fin.noi) : "N/A"} highlight={fin.noi > 0} />
                      <Stat label="Cap Rate" value={fin.capRate !== "N/A" ? `${fin.capRate}%` : "N/A"} highlight={parseFloat(fin.capRate) > 4} />
                    </div>

                    {p.score.reasons.length > 0 && (
                      <div style={{ fontSize: 12, color: "#16a34a", background: "#f0fdf4", borderRadius: 8, padding: "8px 12px", marginBottom: 14 }}>
                        ✓ {p.score.reasons.join(" · ")}
                      </div>
                    )}

                    <div style={{ display: "flex", gap: 8, flexWrap: "wrap" }}>
                      <button onClick={() => onSelect(p)} style={{ background: "#0f172a", color: "white", border: "none", borderRadius: 8, padding: "10px 18px", fontSize: 13, fontWeight: 600, cursor: "pointer" }}>
                        Full Analysis →
                      </button>
                      <button onClick={() => toggleCompare(p.id)} style={{ background: isComparing ? "#eff6ff" : "white", color: isComparing ? "#1d4ed8" : "#374151", border: isComparing ? "1px solid #3b82f6" : "1px solid #e5e7eb", borderRadius: 8, padding: "10px 18px", fontSize: 13, fontWeight: 600, cursor: "pointer" }}>
                        {isComparing ? "✓ Comparing" : "+ Compare"}
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            );
          })}
        </div>
      </div>
    </div>
  );
};

// --- PROPERTY DETAIL PAGE ---
const DetailPage = ({ property, profile, onBack, onLead }) => {
  const [scenario, setScenario] = useState("base");
  const [aiInsight, setAiInsight] = useState("");
  const [aiLoading, setAiLoading] = useState(false);
  const fin = analyzeFinancials(property, profile, scenario);
  const zoning = analyzeZoning(property);
  const score = scoreProperty(property, profile);

  const getAIInsight = async () => {
    setAiLoading(true);
    setAiInsight("");
    try {
      const prompt = `You are a senior Miami real estate advisor. Analyze this property and give a concise, honest advisory opinion (3-4 paragraphs).

Property: ${property.address}, ${property.neighborhood}, ${property.city}
Type: ${property.propertyType} | Price: $${property.price.toLocaleString()}
Beds/Baths: ${property.beds}/${property.baths} | Sq Ft: ${property.livingArea} | Lot: ${property.lotSize} sf
Zoning: ${property.zoningCode} | HOA: $${property.hoa}/mo
Estimated Rent: $${property.estimatedRent}/mo
Last Sale: $${property.lastSalePrice?.toLocaleString()} (${property.lastSaleDate})
Notes: ${property.notes}

Financial (Base Case):
- Monthly PITI + reserves: $${fin.totalMonthlyCost.toLocaleString()}
- NOI: $${fin.noi.toLocaleString()} annually
- Cap Rate: ${fin.capRate}%
- Cash-on-Cash: ${fin.cashOnCash}%
- Annual Cash Flow: $${fin.annualCashFlow.toLocaleString()}

Zoning Analysis: ${zoning.densityClue} | Max units est: ${zoning.maxUnitsEstimated} | ADU: ${zoning.aduPotential} | Duplex: ${zoning.duplexPotential}

User Profile: ${profile.userType} | Budget: $${profile.budget?.toLocaleString()} | Risk: ${profile.riskTolerance} | Dev interest: ${profile.developmentInterest}

Be honest, specific to Miami market, mention any red flags, and end with a clear recommendation. Do not oversell. Mention assumptions.`;

      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ model: "claude-sonnet-4-20250514", max_tokens: 1000, messages: [{ role: "user", content: prompt }] })
      });
      const data = await res.json();
      setAiInsight(data.content?.[0]?.text || "Unable to generate insight.");
    } catch (e) {
      setAiInsight("Analysis temporarily unavailable. Please try again.");
    }
    setAiLoading(false);
  };

  return (
    <div style={{ minHeight: "100vh", background: "#f8fafc", fontFamily: "sans-serif" }}>
      {/* Header */}
      <div style={{ background: "#0f172a", padding: "20px 32px", display: "flex", justifyContent: "space-between", alignItems: "center" }}>
        <button onClick={onBack} style={{ background: "transparent", color: "#94a3b8", border: "none", cursor: "pointer", fontSize: 14 }}>← Back to Results</button>
        <div style={{ fontSize: 13, color: "#10b981" }}>PROPERTY ANALYSIS</div>
      </div>

      <div style={{ maxWidth: 1000, margin: "0 auto", padding: "32px 24px" }}>
        {/* Hero Card */}
        <div style={{ background: `linear-gradient(135deg, ${property.color}dd, ${property.color}66)`, borderRadius: 20, padding: "32px 36px", marginBottom: 24, color: "white" }}>
          <div style={{ display: "flex", flexWrap: "wrap", gap: 8, marginBottom: 16 }}>
            {property.tags.map(t => <Tag key={t} label={t} />)}
          </div>
          <h1 style={{ fontSize: 28, fontWeight: 700, marginBottom: 8, fontFamily: "Georgia, serif" }}>{property.address}</h1>
          <div style={{ fontSize: 16, opacity: 0.85 }}>{property.city}, FL {property.zipCode} · {property.neighborhood}</div>
          <div style={{ display: "flex", gap: 32, marginTop: 24, flexWrap: "wrap" }}>
            <div><div style={{ fontSize: 32, fontWeight: 800 }}>{fmt(property.price)}</div><div style={{ fontSize: 12, opacity: 0.7 }}>Asking Price</div></div>
            {property.beds > 0 && <div><div style={{ fontSize: 32, fontWeight: 800 }}>{property.beds}/{property.baths}</div><div style={{ fontSize: 12, opacity: 0.7 }}>Bed/Bath</div></div>}
            {property.livingArea > 0 && <div><div style={{ fontSize: 32, fontWeight: 800 }}>{property.livingArea.toLocaleString()}</div><div style={{ fontSize: 12, opacity: 0.7 }}>Sq Ft</div></div>}
            {property.lotSize > 0 && <div><div style={{ fontSize: 32, fontWeight: 800 }}>{property.lotSize.toLocaleString()}</div><div style={{ fontSize: 12, opacity: 0.7 }}>Lot Sq Ft</div></div>}
            <div><div style={{ fontSize: 32, fontWeight: 800, color: "#fbbf24" }}>{score.totalScore}</div><div style={{ fontSize: 12, opacity: 0.7 }}>Match Score</div></div>
          </div>
        </div>

        {/* Match Breakdown */}
        <div style={{ background: "white", borderRadius: 16, border: "1px solid #e5e7eb", padding: 24, marginBottom: 24 }}>
          <h3 style={{ fontSize: 17, fontWeight: 700, marginBottom: 20 }}>Match Breakdown</h3>
          <ScoreBar label="Budget Fit (25%)" value={score.budgetScore} />
          <ScoreBar label="Location Match (20%)" value={score.locationScore} />
          <ScoreBar label="Feature Match (15%)" value={score.featureScore} />
          <ScoreBar label="Investment Fit (20%)" value={score.investmentScore} />
          <ScoreBar label="Development Potential (20%)" value={score.developmentScore} />
        </div>

        {/* Financial Analysis */}
        <div style={{ background: "white", borderRadius: 16, border: "1px solid #e5e7eb", padding: 24, marginBottom: 24 }}>
          <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 20 }}>
            <h3 style={{ fontSize: 17, fontWeight: 700 }}>Financial Analysis</h3>
            <div style={{ display: "flex", gap: 6 }}>
              {["conservative", "base", "aggressive"].map(s => (
                <button key={s} onClick={() => setScenario(s)}
                  style={{ background: scenario === s ? "#0f172a" : "#f3f4f6", color: scenario === s ? "white" : "#374151", border: "none", borderRadius: 8, padding: "8px 14px", fontSize: 12, fontWeight: 600, cursor: "pointer", textTransform: "capitalize" }}>
                  {s}
                </button>
              ))}
            </div>
          </div>

          <div style={{ background: "#f0fdf4", border: "1px solid #bbf7d0", borderRadius: 12, padding: "12px 16px", marginBottom: 20, fontSize: 13, color: "#166534" }}>
            {scenario === "conservative" ? "Conservative: Rent -12%, Rate +0.5%. Assumes higher vacancy and slower lease-up." : scenario === "aggressive" ? "Aggressive: Rent +12%, Rate -0.25%. Assumes optimal occupancy and strong Miami rent growth." : "Base Case: Current market estimates with standard assumptions."}
          </div>

          <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit, minmax(160px, 1fr))", gap: 12, marginBottom: 20 }}>
            <Stat label="Loan Amount" value={fmt(fin.loanAmount)} sub={`${property.price > 0 ? Math.round((1 - fin.loanAmount / property.price) * 100) : 0}% down`} />
            <Stat label="Mortgage P&I" value={fmt(fin.mortgagePI) + "/mo"} sub={`@ ${fin.rate}% rate`} />
            <Stat label="Taxes + Ins" value={fmt(fin.taxesMonthly + fin.insuranceMonthly) + "/mo"} />
            <Stat label="HOA" value={fin.hoaMonthly > 0 ? fmt(fin.hoaMonthly) + "/mo" : "None"} />
            <Stat label="Total Monthly" value={fmt(fin.totalMonthlyCost)} highlight />
          </div>

          {property.estimatedRent > 0 && (
            <>
              <div style={{ borderTop: "1px solid #e5e7eb", paddingTop: 20, marginBottom: 20 }}>
                <div style={{ fontSize: 14, fontWeight: 600, color: "#374151", marginBottom: 12 }}>Rental Income Analysis</div>
                <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit, minmax(160px, 1fr))", gap: 12 }}>
                  <Stat label="Est. Monthly Rent" value={fmt(fin.monthlyRent)} />
                  <Stat label="Gross Annual Income" value={fmt(fin.grossIncome)} />
                  <Stat label="Operating Expenses" value={fmt(fin.operatingExpenses)} />
                  <Stat label="Net Operating Income" value={fmt(fin.noi)} highlight={fin.noi > 0} />
                  <Stat label="Annual Cash Flow" value={fmt(fin.annualCashFlow)} highlight={fin.annualCashFlow > 0} />
                </div>
              </div>
              <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit, minmax(160px, 1fr))", gap: 12 }}>
                <Stat label="Cap Rate" value={fin.capRate !== "N/A" ? `${fin.capRate}%` : "N/A"} highlight={parseFloat(fin.capRate) > 4} />
                <Stat label="Cash-on-Cash" value={fin.cashOnCash !== "N/A" ? `${fin.cashOnCash}%` : "N/A"} highlight={parseFloat(fin.cashOnCash) > 6} />
                <Stat label="Est. ROI" value={fin.roi !== "N/A" ? `${fin.roi}%` : "N/A"} />
                <Stat label="Down Payment" value={fmt(fin.downPaymentAmt)} sub="Required upfront" />
              </div>
            </>
          )}
          <div style={{ marginTop: 16, fontSize: 12, color: "#9ca3af", fontStyle: "italic" }}>
            * Financial projections are estimates only. Consult a licensed advisor before making decisions. Assumes 30-year fixed, {fin.rate}% rate, {property.estimatedRent > 0 ? "8% vacancy, 10% management fee, 1% annual maintenance reserve." : "1% annual maintenance reserve."}
          </div>
        </div>

        {/* Zoning Analysis */}
        <div style={{ background: "white", borderRadius: 16, border: "1px solid #e5e7eb", padding: 24, marginBottom: 24 }}>
          <h3 style={{ fontSize: 17, fontWeight: 700, marginBottom: 16 }}>Zoning & Development Potential</h3>
          <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit, minmax(150px, 1fr))", gap: 12, marginBottom: 20 }}>
            <Stat label="Zoning Code" value={zoning.zoningCode} />
            <Stat label="Est. Max Units" value={zoning.maxUnitsEstimated} highlight={zoning.maxUnitsEstimated > 1} />
            <Stat label="ADU Potential" value={zoning.aduPotential ? "Likely" : "Unlikely"} highlight={zoning.aduPotential} />
            <Stat label="Duplex Potential" value={zoning.duplexPotential ? "Possible" : "Unlikely"} highlight={zoning.duplexPotential} />
            <Stat label="Multifamily" value={zoning.multifamilyPotential ? "Possible" : "Unlikely"} highlight={zoning.multifamilyPotential} />
          </div>
          <div style={{ background: "#f8fafc", borderRadius: 10, padding: "14px 16px", marginBottom: 14 }}>
            <div style={{ fontWeight: 600, marginBottom: 6, fontSize: 14 }}>{zoning.densityClue}</div>
            <p style={{ fontSize: 14, color: "#4b5563", lineHeight: 1.7, margin: 0 }}>{zoning.explanation}</p>
          </div>
          <div style={{ background: "#fffbeb", border: "1px solid #fde68a", borderRadius: 10, padding: "12px 16px" }}>
            <div style={{ fontSize: 12, fontWeight: 600, color: "#92400e", marginBottom: 6 }}>⚠ IMPORTANT DISCLAIMER</div>
            {zoning.warnings.map((w, i) => <div key={i} style={{ fontSize: 12, color: "#78350f", marginBottom: 4 }}>• {w}</div>)}
            <div style={{ fontSize: 12, color: "#78350f", marginTop: 8 }}>Verify at: Miami-Dade Property Search · City of Miami Miami 21 Code · Gridics Zoning Map</div>
          </div>
        </div>

        {/* AI Advisory */}
        <div style={{ background: "white", borderRadius: 16, border: "1px solid #e5e7eb", padding: 24, marginBottom: 24 }}>
          <h3 style={{ fontSize: 17, fontWeight: 700, marginBottom: 16 }}>AI Advisory Opinion</h3>
          {!aiInsight && !aiLoading && (
            <div style={{ textAlign: "center", padding: "24px 0" }}>
              <p style={{ color: "#6b7280", marginBottom: 16, fontSize: 14 }}>Get a personalized AI analysis based on your profile and this property's financials.</p>
              <button onClick={getAIInsight} style={{ background: "linear-gradient(135deg, #10b981, #059669)", color: "white", border: "none", borderRadius: 12, padding: "14px 28px", fontSize: 15, fontWeight: 600, cursor: "pointer" }}>
                Generate AI Advisory →
              </button>
            </div>
          )}
          {aiLoading && (
            <div style={{ textAlign: "center", padding: "32px 0", color: "#6b7280" }}>
              <div style={{ fontSize: 24, marginBottom: 12 }}>⟳</div>
              <div>Analyzing property against Miami market conditions...</div>
            </div>
          )}
          {aiInsight && (
            <div style={{ fontSize: 14, lineHeight: 1.8, color: "#374151", whiteSpace: "pre-wrap" }}>{aiInsight}</div>
          )}
        </div>

        {/* Lead Capture */}
        <div style={{ background: "linear-gradient(135deg, #0f172a, #1e293b)", borderRadius: 20, padding: "36px 32px", color: "white", textAlign: "center" }}>
          <div style={{ fontSize: 13, color: "#10b981", marginBottom: 12, letterSpacing: "0.5px" }}>READY TO MOVE FORWARD?</div>
          <h3 style={{ fontSize: 26, fontWeight: 700, marginBottom: 12, fontFamily: "Georgia, serif" }}>Talk to a Miami Real Estate Advisor</h3>
          <p style={{ color: "#94a3b8", marginBottom: 28, maxWidth: 480, margin: "0 auto 28px" }}>Our licensed team can verify zoning, run comps, structure financing, and negotiate on your behalf.</p>
          <button onClick={onLead} style={{ background: "linear-gradient(135deg, #10b981, #059669)", color: "white", border: "none", borderRadius: 12, padding: "16px 36px", fontSize: 16, fontWeight: 600, cursor: "pointer", boxShadow: "0 4px 24px rgba(16,185,129,0.4)" }}>
            Connect with an Advisor →
          </button>
        </div>
      </div>
    </div>
  );
};

// --- COMPARE PAGE ---
const ComparePage = ({ properties, profile, onBack }) => {
  if (!properties || properties.length < 2) return null;
  const fins = properties.map(p => analyzeFinancials(p, profile));
  const zonings = properties.map(p => analyzeZoning(p));
  const scores = properties.map(p => scoreProperty(p, profile));
  const bestOverall = scores.indexOf(scores.reduce((best, s) => s.totalScore > best.totalScore ? s : best, scores[0]));
  const bestCashFlow = fins.indexOf(fins.reduce((best, f) => f.annualCashFlow > best.annualCashFlow ? f : best, fins[0]));
  const bestDev = zonings.indexOf(zonings.reduce((best, z) => z.maxUnitsEstimated > best.maxUnitsEstimated ? z : best, zonings[0]));

  const rows = [
    { label: "Price", vals: fins.map((f, i) => fmt(properties[i].price)) },
    { label: "Monthly Cost", vals: fins.map(f => fmt(f.totalMonthlyCost)) },
    { label: "Est Rent", vals: properties.map(p => p.estimatedRent > 0 ? fmt(p.estimatedRent) : "N/A") },
    { label: "NOI", vals: fins.map(f => f.noi > 0 ? fmt(f.noi) : "N/A") },
    { label: "Cap Rate", vals: fins.map(f => f.capRate !== "N/A" ? `${f.capRate}%` : "N/A") },
    { label: "Cash-on-Cash", vals: fins.map(f => f.cashOnCash !== "N/A" ? `${f.cashOnCash}%` : "N/A") },
    { label: "Zoning", vals: properties.map(p => p.zoningCode) },
    { label: "Max Units (est)", vals: zonings.map(z => z.maxUnitsEstimated) },
    { label: "Lot Size", vals: properties.map(p => p.lotSize > 0 ? `${p.lotSize.toLocaleString()} sf` : "N/A") },
    { label: "Match Score", vals: scores.map(s => s.totalScore) },
  ];

  return (
    <div style={{ minHeight: "100vh", background: "#f8fafc", fontFamily: "sans-serif" }}>
      <div style={{ background: "#0f172a", padding: "20px 32px", display: "flex", justifyContent: "space-between", alignItems: "center" }}>
        <button onClick={onBack} style={{ background: "transparent", color: "#94a3b8", border: "none", cursor: "pointer", fontSize: 14 }}>← Back</button>
        <div style={{ fontSize: 13, color: "#10b981" }}>PROPERTY COMPARISON</div>
      </div>
      <div style={{ maxWidth: 1100, margin: "0 auto", padding: "32px 24px" }}>
        {/* Headers */}
        <div style={{ display: "grid", gridTemplateColumns: `200px ${properties.map(() => "1fr").join(" ")}`, gap: 12, marginBottom: 4 }}>
          <div />
          {properties.map((p, i) => (
            <div key={p.id} style={{ background: `linear-gradient(135deg, ${p.color}cc, ${p.color}44)`, borderRadius: 14, padding: "20px 16px", color: "white", textAlign: "center" }}>
              {[i === bestOverall && "🏆 Best Overall", i === bestCashFlow && "💰 Best Cash Flow", i === bestDev && "🏗️ Most Dev. Upside"].filter(Boolean).map(badge => (
                <div key={badge} style={{ background: "rgba(255,255,255,0.2)", borderRadius: 99, fontSize: 10, padding: "3px 8px", marginBottom: 6, display: "inline-block" }}>{badge}</div>
              ))}
              <div style={{ fontSize: 14, fontWeight: 700, marginBottom: 4 }}>{p.address.split(",")[0]}</div>
              <div style={{ fontSize: 12, opacity: 0.8 }}>{p.neighborhood}</div>
              <div style={{ fontSize: 20, fontWeight: 800, marginTop: 8 }}>{fmt(p.price)}</div>
            </div>
          ))}
        </div>

        {/* Rows */}
        {rows.map((row, ri) => (
          <div key={row.label} style={{ display: "grid", gridTemplateColumns: `200px ${properties.map(() => "1fr").join(" ")}`, gap: 12, marginBottom: 4 }}>
            <div style={{ background: ri % 2 === 0 ? "#f3f4f6" : "white", borderRadius: 8, padding: "12px 14px", fontSize: 13, fontWeight: 600, color: "#374151", display: "flex", alignItems: "center" }}>{row.label}</div>
            {row.vals.map((v, i) => (
              <div key={i} style={{ background: ri % 2 === 0 ? "#f3f4f6" : "white", borderRadius: 8, padding: "12px 14px", fontSize: 14, fontWeight: 500, textAlign: "center", color: "#111827" }}>{v}</div>
            ))}
          </div>
        ))}
      </div>
    </div>
  );
};

// --- LEAD CAPTURE ---
const LeadPage = ({ property, profile, onBack }) => {
  const [form, setForm] = useState({ name: "", email: "", phone: "", notes: "" });
  const [submitted, setSubmitted] = useState(false);

  if (submitted) return (
    <div style={{ minHeight: "100vh", background: "#0f172a", display: "flex", alignItems: "center", justifyContent: "center", fontFamily: "sans-serif" }}>
      <div style={{ textAlign: "center", maxWidth: 480 }}>
        <div style={{ fontSize: 64, marginBottom: 24 }}>✅</div>
        <h2 style={{ color: "#f1f5f9", fontSize: 28, fontWeight: 700, marginBottom: 16, fontFamily: "Georgia, serif" }}>You're on our radar.</h2>
        <p style={{ color: "#94a3b8", fontSize: 16, lineHeight: 1.7, marginBottom: 32 }}>A licensed Miami advisor will reach out within 1 business day to discuss your goals, verify zoning, and build your custom buy box.</p>
        <button onClick={onBack} style={{ background: "linear-gradient(135deg, #10b981, #059669)", color: "white", border: "none", borderRadius: 12, padding: "14px 28px", fontSize: 15, fontWeight: 600, cursor: "pointer" }}>← Continue Exploring</button>
      </div>
    </div>
  );

  return (
    <div style={{ minHeight: "100vh", background: "#0f172a", display: "flex", alignItems: "center", justifyContent: "center", padding: 24, fontFamily: "sans-serif" }}>
      <div style={{ maxWidth: 520, width: "100%" }}>
        <button onClick={onBack} style={{ background: "transparent", color: "#94a3b8", border: "none", cursor: "pointer", fontSize: 14, marginBottom: 24 }}>← Back</button>
        <div style={{ background: "#1e293b", border: "1px solid #334155", borderRadius: 20, padding: 40 }}>
          <div style={{ fontSize: 13, color: "#10b981", marginBottom: 12, letterSpacing: "0.5px" }}>CONNECT WITH AN ADVISOR</div>
          <h2 style={{ fontSize: 26, color: "#f1f5f9", fontWeight: 700, marginBottom: 8, fontFamily: "Georgia, serif" }}>Build Your Investment Plan</h2>
          {property && <p style={{ color: "#64748b", fontSize: 14, marginBottom: 24 }}>Interested in: {property.address} · {fmt(property.price)}</p>}

          <div style={{ display: "flex", flexDirection: "column", gap: 14 }}>
            {[{ id: "name", label: "Full Name", placeholder: "Jane Smith" }, { id: "email", label: "Email", placeholder: "jane@email.com" }, { id: "phone", label: "Phone", placeholder: "(305) 555-0100" }].map(f => (
              <div key={f.id}>
                <label style={{ fontSize: 13, color: "#94a3b8", display: "block", marginBottom: 6 }}>{f.label}</label>
                <input value={form[f.id]} onChange={e => setForm(p => ({ ...p, [f.id]: e.target.value }))} placeholder={f.placeholder}
                  style={{ width: "100%", background: "#0f172a", border: "1px solid #334155", borderRadius: 10, padding: "12px 14px", color: "#f1f5f9", fontSize: 15, boxSizing: "border-box", fontFamily: "sans-serif" }} />
              </div>
            ))}
            <div>
              <label style={{ fontSize: 13, color: "#94a3b8", display: "block", marginBottom: 6 }}>Anything else you want us to know?</label>
              <textarea value={form.notes} onChange={e => setForm(p => ({ ...p, notes: e.target.value }))} placeholder="Questions, constraints, or goals..."
                style={{ width: "100%", background: "#0f172a", border: "1px solid #334155", borderRadius: 10, padding: "12px 14px", color: "#f1f5f9", fontSize: 15, minHeight: 80, boxSizing: "border-box", fontFamily: "sans-serif", resize: "vertical" }} />
            </div>
            <button onClick={() => form.name && form.email && setSubmitted(true)}
              style={{ background: form.name && form.email ? "linear-gradient(135deg, #10b981, #059669)" : "#334155", color: form.name && form.email ? "white" : "#64748b", border: "none", borderRadius: 12, padding: "16px", fontSize: 16, fontWeight: 600, cursor: form.name && form.email ? "pointer" : "not-allowed", marginTop: 8 }}>
              Request Advisor Consultation →
            </button>
          </div>

          <div style={{ marginTop: 20, fontSize: 12, color: "#475569", textAlign: "center" }}>
            No pressure. No spam. Your information is only shared with our licensed advisors.
          </div>
        </div>
      </div>
    </div>
  );
};

// ============================================================
// SIMULADOR DE CASH FLOW — "¿Qué pasa si...?" v2
// ============================================================

// ── Utilidades numéricas compartidas ──
const fmtUSD  = v => `$${Math.round(Math.abs(v)).toLocaleString()}`;
const fmtSign = v => `${v >= 0 ? "+" : "-"}$${Math.round(Math.abs(v)).toLocaleString()}`;
const calcMPI = (principal, annualRate, years) => {
  if (!principal || !annualRate) return 0;
  const r = annualRate / 100 / 12, n = years * 12;
  return Math.round(principal * (r * Math.pow(1+r,n)) / (Math.pow(1+r,n)-1));
};
const calcNOI = (rentaTotal, taxes, ins, hoa, maint, vacPct = 0.08, adminPct = 0.10) => {
  const vac   = Math.round(rentaTotal * vacPct);
  const admin = Math.round(rentaTotal * adminPct);
  return Math.round(rentaTotal * 12 - (taxes + ins + hoa + maint + vac + admin) * 12);
};

// ── Slider reutilizable ──
const SSlider = ({ label, value, min, max, step = 1, onChange, fmt = v => String(v), color = "#0e7490", badge }) => (
  <div style={{ marginBottom: 16 }}>
    <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 5 }}>
      <span style={{ fontSize: 13, color: "#374151", fontWeight: 500 }}>{label}</span>
      <span style={{ fontSize: 14, fontWeight: 800, color, background: `${color}15`, padding: "2px 10px", borderRadius: 99 }}>
        {fmt(value)}{badge ? <span style={{ fontSize: 10, marginLeft: 4, opacity: 0.7 }}>{badge}</span> : null}
      </span>
    </div>
    <input type="range" min={min} max={max} step={step} value={value}
      onChange={e => onChange(Number(e.target.value))}
      style={{ width: "100%", accentColor: color, height: 4 }} />
    <div style={{ display: "flex", justifyContent: "space-between", fontSize: 10, color: "#9ca3af", marginTop: 1 }}>
      <span>{fmt(min)}</span><span>{fmt(max)}</span>
    </div>
  </div>
);

// ── Tarjeta de KPI compacta ──
const KPI = ({ label, value, sub, good, neutral }) => {
  const bg = neutral ? "#f9fafb" : good ? "#f0fdf4" : "#fef2f2";
  const clr = neutral ? "#111827" : good ? "#15803d" : "#dc2626";
  const border = neutral ? "#e5e7eb" : good ? "#bbf7d0" : "#fca5a5";
  return (
    <div style={{ background: bg, border: `1px solid ${border}`, borderRadius: 10, padding: "10px 12px" }}>
      <div style={{ fontSize: 10, color: "#6b7280", textTransform: "uppercase", letterSpacing: "0.4px", marginBottom: 3 }}>{label}</div>
      <div style={{ fontSize: 17, fontWeight: 800, color: clr }}>{value}</div>
      {sub && <div style={{ fontSize: 10, color: "#9ca3af", marginTop: 2 }}>{sub}</div>}
    </div>
  );
};

// ── Fila de comparación antes → después ──
const CRow = ({ label, a, b: bVal, fmt = fmtUSD }) => {
  const up = bVal > a, same = bVal === a;
  return (
    <div style={{ display: "grid", gridTemplateColumns: "1fr 80px 80px", alignItems: "center", padding: "8px 0", borderBottom: "1px solid #f3f4f6", gap: 4 }}>
      <div style={{ fontSize: 12, color: "#6b7280" }}>{label}</div>
      <div style={{ fontSize: 12, fontWeight: 600, color: "#374151", textAlign: "center" }}>{fmt(a)}</div>
      <div style={{ fontSize: 12, fontWeight: 700, color: same ? "#374151" : up ? "#16a34a" : "#dc2626", textAlign: "right" }}>
        {same ? "—" : (up ? "▲ " : "▼ ")}{fmt(bVal)}
      </div>
    </div>
  );
};

const SimuladorCashFlow = ({ property, profile, zoningInfo }) => {
  const base = property;

  // ── PANEL 1: Condiciones de financiamiento dinámicas ──
  const [tasa,    setTasa]    = useState(7.25);
  const [downPct, setDownPct] = useState(profile.downPayment || 20);
  const [plazoHip,setPlazoHip]= useState(30);
  const [vacPct,  setVacPct]  = useState(8);
  const [adminPct,setAdminPct]= useState(10);

  // ── PANEL 2 – 5: mejoras ──
  const [modo, setModo] = useState("financiamiento"); // financiamiento | split | habitacion | adu | precio_renta | break_even
  const [unidades,    setUnidades]    = useState(1);
  const [rentaExtra,  setRentaExtra]  = useState(700);
  const [costoObra,   setCostoObra]   = useState(0);
  const [tasaObra,    setTasaObra]    = useState(8);
  const [plazoObra,   setPlazoObra]   = useState(24);
  const [rentaAjuste, setRentaAjuste] = useState(base.estimatedRent || 0);

  // ── House-split configurador ──
  const totalBeds  = base.beds  || 3;
  const totalBaths = base.baths || 2;

  // Genera configuraciones automáticas de split basadas en beds/baths reales
  const genSplits = (beds, baths) => {
    const splits = [];
    // Opción 0: sin split (actual)
    splits.push({
      id: "nosplit",
      label: `Sin dividir — ${beds}/${baths} completo`,
      units: [{ label: `Unidad completa ${beds}b/${baths}ba`, beds, baths, rentaRef: 0 }],
      costoEstimado: 0,
    });
    // Si beds >= 2: split en 1+resto
    if (beds >= 2) {
      const b1 = 1, ba1 = 1;
      const b2 = beds - 1, ba2 = Math.max(1, baths - 1);
      splits.push({
        id: "split_1_resto",
        label: `Suite principal + ${b2}b/${ba2}ba`,
        units: [
          { label: `Suite ${b1}b/${ba1}ba`, beds: b1, baths: ba1, rentaRef: 0 },
          { label: `${b2}b/${ba2}ba`, beds: b2, baths: ba2, rentaRef: 0 },
        ],
        costoEstimado: 12000,
      });
    }
    // Si beds >= 3: split en dos unidades iguales
    if (beds >= 3) {
      const b1 = Math.floor(beds / 2), ba1 = Math.max(1, Math.floor(baths / 2));
      const b2 = beds - b1, ba2 = baths - ba1 > 0 ? baths - ba1 : 1;
      splits.push({
        id: "split_mitad",
        label: `${b1}b/${ba1}ba + ${b2}b/${ba2}ba`,
        units: [
          { label: `Unidad A ${b1}b/${ba1}ba`, beds: b1, baths: ba1, rentaRef: 0 },
          { label: `Unidad B ${b2}b/${ba2}ba`, beds: b2, baths: ba2, rentaRef: 0 },
        ],
        costoEstimado: 18000,
      });
    }
    // Si beds >= 4: tres unidades
    if (beds >= 4) {
      splits.push({
        id: "split_tres",
        label: `3 unidades: 1b/1ba · 1b/1ba · ${beds - 2}b/${Math.max(1, baths - 2)}ba`,
        units: [
          { label: "Unidad A 1b/1ba", beds: 1, baths: 1, rentaRef: 0 },
          { label: "Unidad B 1b/1ba", beds: 1, baths: 1, rentaRef: 0 },
          { label: `Unidad C ${beds - 2}b/${Math.max(1, baths - 2)}ba`, beds: beds - 2, baths: Math.max(1, baths - 2), rentaRef: 0 },
        ],
        costoEstimado: 32000,
      });
    }
    // Cuartos por separado (shared house / rooming)
    splits.push({
      id: "rooming",
      label: `Rooming house — ${beds} cuartos individuales`,
      units: Array.from({ length: beds }, (_, i) => ({ label: `Cuarto ${i + 1}`, beds: 1, baths: 0, rentaRef: 0 })),
      costoEstimado: beds * 3500,
    });
    return splits;
  };

  const SPLITS = genSplits(totalBeds, totalBaths);
  const [splitIdx, setSplitIdx]   = useState(0);
  // Renta por unidad en el split seleccionado (editable)
  const [splitRentas, setSplitRentas] = useState({});

  // Referencia de renta por tamaño en Miami
  const rentaRefMiami = (beds, baths) => {
    if (beds === 0) return 900;   // cuarto
    if (beds === 1) return 2100;
    if (beds === 2) return 2900;
    if (beds === 3) return 3700;
    return 4500;
  };

  const getSplitRenta = (unitId, beds, baths) => {
    if (splitRentas[unitId] !== undefined) return splitRentas[unitId];
    return rentaRefMiami(beds, baths);
  };

  // ── CÁLCULO BASE con financiamiento dinámico ──
  const loan    = base.price * (1 - downPct / 100);
  const mpi     = calcMPI(loan, tasa, plazoHip);
  const taxes   = Math.round(base.taxes / 12);
  const ins     = Math.round(base.insuranceEstimate / 12);
  const hoa     = base.hoa || 0;
  const maint   = Math.round(base.price * 0.01 / 12);
  const rentaBase = base.estimatedRent || 0;
  const noiBase   = calcNOI(rentaBase, taxes, ins, hoa, maint, vacPct / 100, adminPct / 100);
  const flujoBase = noiBase - mpi * 12;
  const downAmt   = Math.round(base.price * downPct / 100);
  const capBase   = base.price > 0 && noiBase > 0 ? ((noiBase / base.price) * 100).toFixed(2) : "N/A";
  const cocBase   = downAmt > 0 ? ((flujoBase / downAmt) * 100).toFixed(1) : "N/A";
  const totalMensual = mpi + taxes + ins + hoa + maint;

  // ── CÁLCULO SIMULADO según modo ──
  const cuotaObra = costoObra > 0
    ? calcMPI(costoObra, Math.max(tasaObra, 0.01), plazoObra / 12)
    : 0;

  let rentaSim = rentaBase;
  if (modo === "habitacion") rentaSim = rentaBase + unidades * rentaExtra;
  if (modo === "adu")        rentaSim = rentaBase + unidades * rentaExtra;
  if (modo === "precio_renta") rentaSim = rentaAjuste;
  if (modo === "split") {
    const split = SPLITS[splitIdx];
    rentaSim = split.units.reduce((sum, u, i) => sum + getSplitRenta(`${split.id}_${i}`, u.beds, u.baths), 0);
  }

  const noiSim   = calcNOI(rentaSim, taxes, ins, hoa, maint, vacPct / 100, adminPct / 100);
  const flujoSim = noiSim - mpi * 12 - cuotaObra * 12;
  const capSim   = base.price > 0 && noiSim > 0 ? ((noiSim / base.price) * 100).toFixed(2) : "N/A";
  const cocSim   = downAmt > 0 ? ((flujoSim / downAmt) * 100).toFixed(1) : "N/A";

  const gastosFijos12 = (taxes + ins + hoa + maint) * 12;
  const breakEven = Math.ceil((mpi * 12 + gastosFijos12 + cuotaObra * 12) / (12 * (1 - vacPct / 100 - adminPct / 100)));

  const mejoroFlujo = flujoSim > flujoBase;
  const positivo    = flujoSim >= 0;
  const diferencia  = flujoSim - flujoBase;

  const roiObra = costoObra > 0 && diferencia > 0
    ? ((diferencia / costoObra) * 100).toFixed(1)
    : null;

  // ── Gauge de flujo ──
  const FlujoGauge = ({ valor, label = "flujo anual" }) => {
    const MAX = Math.max(Math.abs(flujoBase), Math.abs(flujoSim), 24000, 1);
    const pct  = Math.min(Math.abs(valor) / MAX * 100, 100);
    const pos  = valor >= 0;
    return (
      <div style={{ textAlign: "center" }}>
        <div style={{ fontSize: 30, fontWeight: 900, color: pos ? "#16a34a" : "#dc2626", fontVariantNumeric: "tabular-nums" }}>
          {fmtSign(valor)}<span style={{ fontSize: 14, fontWeight: 400 }}>/año</span>
        </div>
        <div style={{ fontSize: 11, color: "#6b7280", marginBottom: 6 }}>{label}</div>
        <div style={{ background: "#f3f4f6", borderRadius: 99, height: 12, overflow: "hidden", position: "relative" }}>
          <div style={{ position: "absolute", left: "50%", top: 0, bottom: 0, width: 2, background: "#d1d5db" }} />
          <div style={{ width: `${pct / 2}%`, height: 12, background: pos ? "linear-gradient(90deg,#10b981,#34d399)" : "linear-gradient(90deg,#ef4444,#fca5a5)", borderRadius: 99, marginLeft: pos ? "50%" : `${50 - pct / 2}%`, transition: "all 0.5s ease" }} />
        </div>
        <div style={{ display: "flex", justifyContent: "space-between", fontSize: 10, color: "#9ca3af", marginTop: 3 }}>
          <span>Negativo</span><span>Break-even</span><span>Positivo</span>
        </div>
      </div>
    );
  };

  const MODOS = [
    { key: "financiamiento", label: "Financiamiento", icon: "🏦" },
    { key: "split",          label: "Dividir unidades", icon: "🔀" },
    { key: "habitacion",     label: "Agregar cuartos", icon: "🛏️" },
    { key: "adu",            label: "ADU",             icon: "🏠" },
    { key: "precio_renta",   label: "Ajustar renta",  icon: "💵" },
    { key: "break_even",     label: "Break-even",     icon: "⚖️" },
  ];

  // ── STATE ALREADY DECLARED ABOVE ── (tasa, downPct, plazoHip, etc.)

  return (
    <div style={{ background: "white", borderRadius: 20, border: "2px solid #a5f3fc", marginBottom: 16, overflow: "hidden" }}>
      {/* Header */}
      <div style={{ background: "linear-gradient(135deg, #0c4a6e, #0e7490)", padding: "18px 24px" }}>
        <div style={{ fontSize: 11, color: "#67e8f9", letterSpacing: "0.5px", marginBottom: 4 }}>SIMULADOR INTERACTIVO</div>
        <h3 style={{ fontSize: 19, fontWeight: 700, color: "white", margin: 0, fontFamily: "Georgia, serif" }}>
          ¿Qué pasa si…? — Optimizador de Cash Flow
        </h3>
        <div style={{ fontSize: 12, color: "rgba(255,255,255,0.6)", marginTop: 3 }}>
          Mové los controles y mirá el impacto en tiempo real en tu flujo de caja
        </div>
      </div>

      {/* Tabs */}
      <div style={{ display: "flex", overflowX: "auto", borderBottom: "1px solid #e5e7eb", background: "#f8fafc" }}>
        {MODOS.map(m => (
          <button key={m.key} onClick={() => setModo(m.key)}
            style={{ flexShrink: 0, padding: "12px 14px", background: modo === m.key ? "white" : "transparent", border: "none", borderBottom: modo === m.key ? "2px solid #0e7490" : "2px solid transparent", cursor: "pointer", fontSize: 11, fontWeight: modo === m.key ? 700 : 400, color: modo === m.key ? "#0e7490" : "#6b7280", display: "flex", flexDirection: "column", alignItems: "center", gap: 3, whiteSpace: "nowrap" }}>
            <span style={{ fontSize: 16 }}>{m.icon}</span>{m.label}
          </button>
        ))}
      </div>

      <div style={{ padding: "20px 22px" }}>
        <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 24, alignItems: "start" }}>

          {/* ─── PANEL IZQUIERDO ─── */}
          <div>

            {/* ── FINANCIAMIENTO ── */}
            {modo === "financiamiento" && (
              <div>
                <div style={{ fontSize: 13, fontWeight: 700, color: "#0c4a6e", marginBottom: 14 }}>🏦 Modificá las condiciones del préstamo</div>
                <SSlider label="Tasa de interés (%)" value={tasa} min={4} max={12} step={0.25} onChange={setTasa} fmt={v => `${v}%`} color="#0e7490" />
                <SSlider label="Enganche / Down payment" value={downPct} min={3} max={50} step={1} onChange={setDownPct} fmt={v => `${v}%`} color="#0e7490" badge={`$${Math.round(base.price * downPct / 100).toLocaleString()}`} />
                <SSlider label="Plazo del préstamo" value={plazoHip} min={10} max={30} step={5} onChange={setPlazoHip} fmt={v => `${v} años`} color="#0e7490" />
                <div style={{ borderTop: "1px solid #f3f4f6", paddingTop: 14, marginTop: 4 }}>
                  <div style={{ fontSize: 11, fontWeight: 700, color: "#6b7280", marginBottom: 10, textTransform: "uppercase" }}>Supuestos operativos</div>
                  <SSlider label="Tasa de vacancia" value={vacPct} min={0} max={20} step={1} onChange={setVacPct} fmt={v => `${v}%`} color="#7c3aed" />
                  <SSlider label="Fee de administración" value={adminPct} min={0} max={20} step={1} onChange={setAdminPct} fmt={v => `${v}%`} color="#7c3aed" />
                </div>
                <div style={{ fontSize: 11, fontWeight: 700, color: "#6b7280", marginBottom: 6, textTransform: "uppercase" }}>Escenarios rápidos</div>
                <div style={{ display: "flex", gap: 6 }}>
                  {[
                    { label: "FHA 3.5%", t: 7.0,  d: 3.5,  p: 30 },
                    { label: "Conv 20%", t: 7.25, d: 20,   p: 30 },
                    { label: "15 años",  t: 6.75, d: 20,   p: 15 },
                    { label: "+30% down",t: 5.5,  d: 30,   p: 30 },
                  ].map(pr => (
                    <button key={pr.label} onClick={() => { setTasa(pr.t); setDownPct(pr.d); setPlazoHip(pr.p); }}
                      style={{ flex: 1, background: "#f0f9ff", color: "#0369a1", border: "1px solid #bae6fd", borderRadius: 8, padding: "6px 4px", fontSize: 10, fontWeight: 600, cursor: "pointer", textAlign: "center" }}>
                      {pr.label}
                    </button>
                  ))}
                </div>
              </div>
            )}

            {/* ── DIVIDIR UNIDADES ── */}
            {modo === "split" && (
              <div>
                <div style={{ fontSize: 13, fontWeight: 700, color: "#0c4a6e", marginBottom: 6 }}>🔀 Dividir en unidades separadas</div>
                <div style={{ fontSize: 12, color: "#6b7280", marginBottom: 12, lineHeight: 1.6 }}>
                  Esta propiedad tiene <strong>{totalBeds}hab / {totalBaths}ba</strong>. Evaluá cómo dividirla para maximizar el ingreso.
                </div>
                {SPLITS.map((split, idx) => (
                  <button key={split.id} onClick={() => setSplitIdx(idx)}
                    style={{ width: "100%", textAlign: "left", background: splitIdx === idx ? "#f0f9ff" : "#f9fafb", border: `1.5px solid ${splitIdx === idx ? "#0e7490" : "#e5e7eb"}`, borderRadius: 12, padding: "10px 12px", marginBottom: 7, cursor: "pointer" }}>
                    <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 5 }}>
                      <div style={{ fontSize: 12, fontWeight: 700, color: splitIdx === idx ? "#0c4a6e" : "#374151" }}>{split.label}</div>
                      {split.costoEstimado > 0 && (
                        <span style={{ fontSize: 10, background: "#fef3c7", color: "#92400e", padding: "2px 8px", borderRadius: 99, fontWeight: 600 }}>
                          ~${split.costoEstimado.toLocaleString()}
                        </span>
                      )}
                    </div>
                    <div style={{ display: "flex", gap: 4, flexWrap: "wrap" }}>
                      {split.units.map((u, i) => (
                        <span key={i} style={{ background: splitIdx === idx ? "#bae6fd" : "#e5e7eb", color: splitIdx === idx ? "#0c4a6e" : "#6b7280", fontSize: 10, padding: "2px 7px", borderRadius: 99 }}>{u.label}</span>
                      ))}
                    </div>
                  </button>
                ))}
                {splitIdx > 0 && (
                  <div style={{ background: "#f0f9ff", border: "1px solid #bae6fd", borderRadius: 12, padding: "12px", marginTop: 6 }}>
                    <div style={{ fontSize: 11, fontWeight: 700, color: "#0c4a6e", marginBottom: 8 }}>Renta por unidad (editable)</div>
                    {SPLITS[splitIdx].units.map((u, i) => {
                      const uid = `${SPLITS[splitIdx].id}_${i}`;
                      return (
                        <SSlider key={uid} label={u.label} value={getSplitRenta(uid, u.beds, u.baths)}
                          min={500} max={6000} step={50}
                          onChange={v => setSplitRentas(p => ({ ...p, [uid]: v }))}
                          fmt={v => `$${v.toLocaleString()}/mes`} color="#0e7490" />
                      );
                    })}
                    <div style={{ fontSize: 10, color: "#0369a1", borderTop: "1px solid #bae6fd", paddingTop: 7, marginTop: 4 }}>
                      Ref. Miami: 1b/1ba ~$2,100 · 2b/2ba ~$2,900 · 3b/2ba ~$3,700 · Cuarto solo ~$900
                    </div>
                  </div>
                )}
              </div>
            )}

            {/* ── AGREGAR CUARTOS ── */}
            {modo === "habitacion" && (
              <div>
                <div style={{ fontSize: 13, fontWeight: 700, color: "#0c4a6e", marginBottom: 12 }}>🛏️ Agregar cuartos para renta</div>
                <SSlider label="Cuartos a agregar" value={unidades} min={1} max={4} step={1} onChange={setUnidades} fmt={v => `${v} cuarto${v > 1 ? "s" : ""}`} color="#0e7490" />
                <SSlider label="Renta por cuarto/mes" value={rentaExtra} min={400} max={2500} step={50} onChange={setRentaExtra} color="#0e7490" />
                <SSlider label="Costo de remodelación" value={costoObra} min={0} max={100000} step={500} onChange={setCostoObra} color="#7c3aed" />
                {costoObra > 0 && <>
                  <SSlider label="Tasa de la obra (%)" value={tasaObra} min={0} max={25} step={0.5} onChange={setTasaObra} fmt={v => `${v}%`} color="#7c3aed" />
                  <SSlider label="Plazo (meses)" value={plazoObra} min={6} max={60} step={6} onChange={setPlazoObra} fmt={v => `${v}m`} color="#7c3aed" />
                </>}
                <div style={{ display: "flex", gap: 6, flexWrap: "wrap" }}>
                  {[["Cosmético", 8000],["Estándar", 18000],["Premium", 35000]].map(([l, v]) => (
                    <button key={l} onClick={() => setCostoObra(v)}
                      style={{ background: costoObra === v ? "#0e7490" : "#f0f9ff", color: costoObra === v ? "white" : "#0369a1", border: "1px solid #bae6fd", borderRadius: 8, padding: "5px 10px", fontSize: 11, fontWeight: 600, cursor: "pointer" }}>
                      {l}<br />${v.toLocaleString()}
                    </button>
                  ))}
                </div>
              </div>
            )}

            {/* ── ADU ── */}
            {modo === "adu" && (
              <div>
                <div style={{ fontSize: 13, fontWeight: 700, color: "#0c4a6e", marginBottom: 10 }}>🏠 Agregar ADU</div>
                {zoningInfo?.aduPotential
                  ? <div style={{ background: "#d1fae5", border: "1px solid #6ee7b7", borderRadius: 10, padding: "9px 12px", marginBottom: 12, fontSize: 12, color: "#065f46" }}>✓ Potencial ADU según zonificación — verificar con municipio.</div>
                  : <div style={{ background: "#fef3c7", border: "1px solid #fde68a", borderRadius: 10, padding: "9px 12px", marginBottom: 12, fontSize: 12, color: "#92400e" }}>⚠ ADU no confirmada. Verificar con City of Miami.</div>
                }
                <SSlider label="Cantidad de ADUs" value={unidades} min={1} max={3} step={1} onChange={setUnidades} fmt={v => `${v} ADU`} color="#0e7490" />
                <SSlider label="Renta por ADU/mes" value={rentaExtra} min={1200} max={5000} step={100} onChange={setRentaExtra} color="#0e7490" />
                <SSlider label="Costo de construcción" value={costoObra} min={0} max={300000} step={5000} onChange={setCostoObra} color="#7c3aed" />
                {costoObra > 0 && <>
                  <SSlider label="Tasa (%)" value={tasaObra} min={0} max={15} step={0.25} onChange={setTasaObra} fmt={v => `${v}%`} color="#7c3aed" />
                  <SSlider label="Plazo (meses)" value={plazoObra} min={12} max={120} step={12} onChange={setPlazoObra} fmt={v => `${v}m`} color="#7c3aed" />
                </>}
                <div style={{ display: "flex", gap: 6, flexWrap: "wrap" }}>
                  {[["Garaje conv.", 45000],["Modular", 80000],["Nueva", 140000]].map(([l, v]) => (
                    <button key={l} onClick={() => setCostoObra(v)}
                      style={{ background: costoObra === v ? "#0e7490" : "#f0f9ff", color: costoObra === v ? "white" : "#0369a1", border: "1px solid #bae6fd", borderRadius: 8, padding: "5px 10px", fontSize: 11, fontWeight: 600, cursor: "pointer" }}>
                      {l}<br />${v.toLocaleString()}
                    </button>
                  ))}
                </div>
              </div>
            )}

            {/* ── AJUSTAR RENTA ── */}
            {modo === "precio_renta" && (
              <div>
                <div style={{ fontSize: 13, fontWeight: 700, color: "#0c4a6e", marginBottom: 10 }}>💵 Ajustar precio de renta</div>
                <div style={{ background: "#f0f9ff", border: "1px solid #bae6fd", borderRadius: 10, padding: "10px 12px", marginBottom: 12 }}>
                  <div style={{ fontSize: 11, color: "#0369a1", marginBottom: 1 }}>Renta estimada actual</div>
                  <div style={{ fontSize: 20, fontWeight: 800, color: "#0c4a6e" }}>${rentaBase.toLocaleString()}/mes</div>
                </div>
                <SSlider label="Nueva renta mensual" value={rentaAjuste} min={Math.max(500, Math.round(rentaBase * 0.5))} max={Math.round(rentaBase * 2.5)} step={50} onChange={setRentaAjuste} color="#0e7490" />
                <div style={{ display: "flex", gap: 6, marginTop: 8 }}>
                  {[0.8, 1.0, 1.15, 1.3].map(m => (
                    <button key={m} onClick={() => setRentaAjuste(Math.round(rentaBase * m))}
                      style={{ flex: 1, background: rentaAjuste === Math.round(rentaBase * m) ? "#0e7490" : "#f0f9ff", color: rentaAjuste === Math.round(rentaBase * m) ? "white" : "#0369a1", border: "1px solid #bae6fd", borderRadius: 8, padding: "6px 4px", fontSize: 10, fontWeight: 600, cursor: "pointer", textAlign: "center" }}>
                      {m === 1 ? "Actual" : `×${m}`}<br />${Math.round(rentaBase * m).toLocaleString()}
                    </button>
                  ))}
                </div>
              </div>
            )}

            {/* ── BREAK-EVEN ── */}
            {modo === "break_even" && (
              <div>
                <div style={{ fontSize: 13, fontWeight: 700, color: "#0c4a6e", marginBottom: 10 }}>⚖️ ¿Cuánto necesito rentar para no perder?</div>
                <div style={{ background: flujoBase < 0 ? "#fee2e2" : "#d1fae5", border: `1px solid ${flujoBase < 0 ? "#fca5a5" : "#6ee7b7"}`, borderRadius: 12, padding: "12px", marginBottom: 12, textAlign: "center" }}>
                  <div style={{ fontSize: 11, color: flujoBase < 0 ? "#991b1b" : "#065f46", marginBottom: 3 }}>Flujo actual</div>
                  <div style={{ fontSize: 22, fontWeight: 800, color: flujoBase < 0 ? "#dc2626" : "#16a34a" }}>{fmtSign(flujoBase)}/año</div>
                </div>
                <div style={{ background: "#f0f9ff", border: "1px solid #bae6fd", borderRadius: 12, padding: "12px", marginBottom: 12, textAlign: "center" }}>
                  <div style={{ fontSize: 11, color: "#0369a1", marginBottom: 3 }}>Renta mínima para break-even</div>
                  <div style={{ fontSize: 24, fontWeight: 800, color: "#0c4a6e" }}>${breakEven.toLocaleString()}/mes</div>
                  <div style={{ fontSize: 11, color: "#0369a1", marginTop: 3 }}>
                    {breakEven > rentaBase ? `${Math.round(((breakEven / rentaBase) - 1) * 100)}% más que la renta estimada` : "Ya cubrís el break-even ✓"}
                  </div>
                </div>
                <SSlider label="Si además financiás obra ($)" value={costoObra} min={0} max={200000} step={5000} onChange={setCostoObra} color="#7c3aed" />
                {costoObra > 0 && <>
                  <SSlider label="Tasa obra (%)" value={tasaObra} min={0} max={15} step={0.25} onChange={setTasaObra} fmt={v => `${v}%`} color="#7c3aed" />
                  <SSlider label="Plazo (meses)" value={plazoObra} min={12} max={120} step={12} onChange={setPlazoObra} fmt={v => `${v}m`} color="#7c3aed" />
                </>}
              </div>
            )}
          </div>

          {/* ─── PANEL DERECHO: resultados ─── */}
          <div>
            <div style={{ background: positivo ? "#f0fdf4" : "#fef2f2", border: `2px solid ${positivo ? "#86efac" : "#fca5a5"}`, borderRadius: 16, padding: "16px", marginBottom: 12 }}>
              <div style={{ fontSize: 11, fontWeight: 700, letterSpacing: "0.4px", textTransform: "uppercase", color: positivo ? "#166534" : "#991b1b", marginBottom: 8 }}>
                {positivo ? "✓ Cash flow positivo" : "⚠ Cash flow negativo"}
              </div>
              <FlujoGauge valor={modo === "break_even" ? flujoBase : flujoSim} label={modo === "break_even" ? "flujo actual" : "flujo simulado / año"} />
              {modo !== "break_even" && Math.abs(diferencia) > 0 && (
                <div style={{ marginTop: 8, fontSize: 12, color: mejoroFlujo ? "#16a34a" : "#dc2626", fontWeight: 700, textAlign: "center" }}>
                  {mejoroFlujo ? "▲" : "▼"} {fmtUSD(Math.abs(diferencia))}/año respecto al escenario actual
                </div>
              )}
            </div>

            <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 8, marginBottom: 12 }}>
              <KPI label="Hipoteca P&I" value={`$${mpi.toLocaleString()}/mes`} neutral />
              <KPI label="Total mensual" value={`$${totalMensual.toLocaleString()}/mes`} neutral />
              <KPI label="Enganche" value={`$${downAmt.toLocaleString()}`} sub={`${downPct}%`} neutral />
              <KPI label="Préstamo" value={`$${Math.round(loan).toLocaleString()}`} sub={`${tasa}% · ${plazoHip}a`} neutral />
            </div>

            {modo !== "break_even" && (
              <div style={{ background: "#f9fafb", borderRadius: 12, padding: "10px 12px", marginBottom: 12 }}>
                <div style={{ display: "grid", gridTemplateColumns: "1fr 72px 72px", borderBottom: "2px solid #e5e7eb", paddingBottom: 5, marginBottom: 3 }}>
                  <div style={{ fontSize: 10, fontWeight: 700, color: "#6b7280", textTransform: "uppercase" }}>Métrica</div>
                  <div style={{ fontSize: 10, fontWeight: 700, color: "#6b7280", textAlign: "center" }}>Actual</div>
                  <div style={{ fontSize: 10, fontWeight: 700, color: "#0e7490", textAlign: "right" }}>Simulado</div>
                </div>
                <CRow label="Renta mensual" a={rentaBase}                      b={rentaSim} />
                <CRow label="NOI anual"     a={noiBase}                         b={noiSim} />
                <CRow label="Flujo anual"   a={flujoBase}                       b={flujoSim} />
                <CRow label="Cap Rate"      a={parseFloat(capBase)||0}          b={parseFloat(capSim)||0}  fmt={v=>`${(v||0).toFixed(2)}%`} />
                <CRow label="Cash-on-Cash"  a={parseFloat(cocBase)||0}          b={parseFloat(cocSim)||0}  fmt={v=>`${(v||0).toFixed(1)}%`} />
                {cuotaObra > 0 && <CRow label="Cuota obra/mes" a={0} b={cuotaObra} fmt={v => `$${v.toLocaleString()}`} />}
              </div>
            )}

            {roiObra && (
              <div style={{ background: "#eff6ff", border: "1px solid #bfdbfe", borderRadius: 12, padding: "10px 12px", marginBottom: 12 }}>
                <div style={{ fontSize: 10, fontWeight: 700, color: "#1e40af", marginBottom: 3, textTransform: "uppercase" }}>ROI de la obra</div>
                <div style={{ fontSize: 20, fontWeight: 800, color: "#1d4ed8" }}>{roiObra}% anual</div>
                <div style={{ fontSize: 11, color: parseFloat(roiObra) > 10 ? "#16a34a" : "#d97706", fontWeight: 600, marginTop: 3 }}>
                  {parseFloat(roiObra) > 10 ? "✓ ROI supera costo de capital — viable" : "Evaluá si compensa el riesgo"}
                </div>
              </div>
            )}

            {modo !== "break_even" && !positivo && (
              <div style={{ background: "#fffbeb", border: "1px solid #fde68a", borderRadius: 12, padding: "10px 12px" }}>
                <div style={{ fontSize: 11, fontWeight: 700, color: "#92400e", marginBottom: 4 }}>🎯 Para llegar a positivo</div>
                <div style={{ fontSize: 12, color: "#78350f", lineHeight: 1.6 }}>
                  Faltan {fmtUSD(Math.ceil(-flujoSim / 12))}/mes más de renta. Break-even: <strong>${breakEven.toLocaleString()}/mes</strong>.
                </div>
              </div>
            )}
            {modo !== "break_even" && positivo && (
              <div style={{ background: "#d1fae5", border: "1px solid #6ee7b7", borderRadius: 12, padding: "10px 12px" }}>
                <div style={{ fontSize: 11, fontWeight: 700, color: "#065f46", marginBottom: 3 }}>✓ Escenario viable</div>
                <div style={{ fontSize: 12, color: "#047857", lineHeight: 1.6 }}>
                  Generás <strong>${Math.abs(flujoSim).toLocaleString()}/año</strong> · <strong>${Math.round(flujoSim/12).toLocaleString()}/mes</strong> neto.
                </div>
              </div>
            )}
          </div>
        </div>

        <div style={{ marginTop: 14, fontSize: 10, color: "#9ca3af", borderTop: "1px solid #f3f4f6", paddingTop: 10, lineHeight: 1.6 }}>
          * Los costos de obra son referencias para Miami. Simulación con los parámetros configurados. Consultá con contratistas y asesores antes de decidir.
        </div>
      </div>
    </div>
  );
};
// ============================================================
// LINK ANALYZER PAGE
// ============================================================

// Detect source platform from URL
// ============================================================
// LINK ANALYZER — single-click AI extraction + full analysis
// ============================================================

function detectSource(url) {
  if (!url) return "other";
  const u = url.toLowerCase();
  if (u.includes("zillow.com")) return "zillow";
  if (u.includes("redfin.com")) return "redfin";
  if (u.includes("realtor.com")) return "realtor";
  if (u.includes("trulia.com")) return "trulia";
  if (u.includes("loopnet.com")) return "loopnet";
  if (u.includes("crexi.com")) return "crexi";
  return "other";
}

const SOURCE_META = {
  zillow:  { label: "Zillow",       color: "#006aff", bg: "#e6f0ff" },
  redfin:  { label: "Redfin",       color: "#c8200e", bg: "#fde8e6" },
  realtor: { label: "Realtor.com",  color: "#d6001c", bg: "#fde8ea" },
  trulia:  { label: "Trulia",       color: "#5a4fcf", bg: "#ede9fe" },
  loopnet: { label: "LoopNet",      color: "#1a5276", bg: "#d6eaf8" },
  crexi:   { label: "Crexi",        color: "#0d6efd", bg: "#dbeafe" },
  other:   { label: "External",     color: "#374151", bg: "#f3f4f6" },
};

// Build a full property object from AI-extracted JSON
function buildPropertyFromAI(ai, url, source) {
  const price       = Number(ai.price) || 0;
  const beds        = Number(ai.beds)  || 0;
  const baths       = Number(ai.baths) || 0;
  const sqft        = Number(ai.sqft)  || 0;
  const hoa         = Number(ai.hoa)   || 0;
  const lotSize     = Number(ai.lotSize)  || 0;
  const yearBuilt   = Number(ai.yearBuilt)|| 0;
  const propType    = ai.propertyType  || "Single Family";
  const address     = ai.address       || "Property from link";
  const neighborhood= ai.neighborhood  || "Miami";
  const zipCode     = ai.zipCode       || "";
  const zoningCode  = ai.zoningCode    || "RS-1";
  const taxes       = Number(ai.taxes) || Math.round(price * 0.011);
  const insurance   = Number(ai.insurance) || Math.round(price * 0.005);
  let estimatedRent = Number(ai.estimatedRent) || 0;
  if (!estimatedRent && price > 0) {
    if (propType.toLowerCase().includes("condo"))
      estimatedRent = Math.round(sqft > 0 ? sqft * 3.2 : price * 0.0055);
    else if (/duplex|multi/i.test(propType))
      estimatedRent = Math.round(price * 0.0065);
    else
      estimatedRent = Math.round(price * 0.005);
  }
  return {
    id: "LINK-" + Date.now(),
    address, city: "Miami", zipCode, neighborhood,
    propertyType: propType, price, beds, baths,
    livingArea: sqft, lotSize, yearBuilt, hoa,
    taxes, insuranceEstimate: insurance, estimatedRent,
    currentUse: ai.currentUse || "Unknown",
    zoningCode, folio: ai.folio || "Requires lookup",
    lastSalePrice: Number(ai.lastSalePrice) || null,
    lastSaleDate: ai.lastSaleDate || null,
    assessedValue: null,
    notes: ai.notes || "",
    tags: [], color: "#1a4a6b",
    _sourceUrl: url, _source: source,
    _aiExtracted: ai._extractedFields  || [],
    _aiEstimated: ai._estimatedFields  || [],
    _aiMissing:   ai._missingFields    || [],
    _extractionNotes: ai.extractionNotes || "",
  };
}

// Confidence pill
const CPill = ({ label, type }) => {
  const styles = {
    extracted: { bg: "#d1fae5", color: "#065f46", prefix: "✓" },
    estimated:  { bg: "#fef3c7", color: "#92400e", prefix: "~" },
    missing:    { bg: "#fee2e2", color: "#991b1b", prefix: "⚠" },
  };
  const s = styles[type] || styles.missing;
  return (
    <span style={{ background: s.bg, color: s.color, fontSize: 11, fontWeight: 700,
      padding: "2px 9px", borderRadius: 99, whiteSpace: "nowrap" }}>
      {s.prefix} {label}
    </span>
  );
};

// Loading step indicator
const LoadStep = ({ steps, current }) => (
  <div style={{ display: "flex", flexDirection: "column", gap: 10, margin: "24px 0" }}>
    {steps.map((s, i) => {
      const done    = i < current;
      const active  = i === current;
      return (
        <div key={i} style={{ display: "flex", alignItems: "center", gap: 12 }}>
          <div style={{
            width: 28, height: 28, borderRadius: "50%", flexShrink: 0,
            background: done ? "#10b981" : active ? "#3b82f6" : "#e5e7eb",
            display: "flex", alignItems: "center", justifyContent: "center",
            fontSize: 13, color: done || active ? "white" : "#9ca3af", fontWeight: 700,
          }}>
            {done ? "✓" : i + 1}
          </div>
          <div style={{ fontSize: 14, color: done ? "#16a34a" : active ? "#1d4ed8" : "#9ca3af", fontWeight: active ? 600 : 400 }}>
            {s}
            {active && <span style={{ marginLeft: 8, fontSize: 12, color: "#3b82f6" }}>working…</span>}
          </div>
        </div>
      );
    })}
  </div>
);

const LinkAnalyzerPage = ({ profile, onBack, onFullDetail, onLead }) => {
  const [phase, setPhase]         = useState("input");    // input | loading | result | error
  const [url, setUrl]             = useState("");
  const [loadStep, setLoadStep]   = useState(0);
  const [property, setProperty]   = useState(null);
  const [aiReport, setAiReport]   = useState("");
  const [scenario, setScenario]   = useState("base");
  const [errorMsg, setErrorMsg]   = useState("");
  const [editMode, setEditMode]   = useState(false);
  const [editFields, setEditFields] = useState({});

  const source = detectSource(url);

  const LOAD_STEPS = [
    "Reading the listing page",
    "Extracting property data with AI",
    "Running financial analysis",
    "Generating investment report",
  ];

  // Kick off the full pipeline
  const handleAnalyze = async () => {
    if (!url.trim()) return;
    setPhase("loading");
    setLoadStep(0);
    setProperty(null);
    setAiReport(null);
    setErrorMsg("");

    try {
      // ── PASO 1: web_fetch real de la URL ──
      setLoadStep(0);
      const extractPrompt = `Eres un especialista en extracción de datos de listados inmobiliarios. El usuario te da esta URL de una propiedad en venta:

URL: ${url}

INSTRUCCIONES:
1. Usa la herramienta web_search para buscar esta propiedad y obtener sus datos reales del listado.
2. Busca por la dirección o identificadores visibles en la URL.
3. Extrae TODOS los datos reales que aparezcan en el listado.
4. Devuelve ÚNICAMENTE un objeto JSON válido (sin markdown, sin backticks, sin explicación).

JSON requerido:
{
  "address": "dirección completa",
  "neighborhood": "vecindario",
  "city": "ciudad",
  "zipCode": "código postal",
  "propertyType": "Single Family | Condo | Townhouse | Duplex | Multifamily | Mixed Use | Vacant Lot",
  "price": 0,
  "beds": 0,
  "baths": 0,
  "sqft": 0,
  "lotSize": 0,
  "yearBuilt": 0,
  "hoa": 0,
  "taxes": 0,
  "insurance": 0,
  "zoningCode": "",
  "folio": "",
  "currentUse": "Owner Occupied | Rental | Vacant | Unknown",
  "lastSalePrice": 0,
  "lastSaleDate": "",
  "estimatedRent": 0,
  "description": "descripción real del listado",
  "features": ["lista", "de", "características"],
  "daysOnMarket": 0,
  "pricePerSqft": 0,
  "listingAgent": "",
  "mlsId": "",
  "notes": "notas del listado",
  "_extractedFields": ["campos","realmente","encontrados","en","el","listado"],
  "_estimatedFields": ["campos","que","tuviste","que","estimar"],
  "_missingFields": ["campos","no","disponibles"],
  "extractionNotes": "nota breve sobre calidad de datos y qué no se pudo encontrar"
}

REGLAS CRÍTICAS:
- Usa SOLO datos reales del listado para _extractedFields.
- Para campos no encontrados, estima con conocimiento del mercado de Miami y márcalos en _estimatedFields.
- estimatedRent: si no aparece en el listado, estima basado en tipo, tamaño y precio usando comps de Miami.
- taxes: si no aparece, estima al 1.1% anual del precio (promedio Miami-Dade).
- insurance: si no aparece, estima al 0.5% anual (alto por riesgo de huracanes en Miami).
- zoningCode: si no aparece, infiere código probable según tipo y zona (T3/T4/T5/T6/RS-1/SD-2 etc).
- Devuelve SOLO el JSON crudo. Ningún otro texto.`;

      const extractRes = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 2000,
          tools: [{ type: "web_search_20250305", name: "web_search" }],
          messages: [{ role: "user", content: extractPrompt }],
        }),
      });
      const extractData = await extractRes.json();

      // Collect all text blocks (Claude may produce multiple after tool use)
      const allTextBlocks = (extractData.content || [])
        .filter(b => b.type === "text")
        .map(b => b.text)
        .join("\n")
        .trim();

      // Try to find JSON object anywhere in the response
      const jsonMatch = allTextBlocks.match(/\{[\s\S]*\}/);
      let aiData;
      if (jsonMatch) {
        try { aiData = JSON.parse(jsonMatch[0]); } catch {}
      }

      // Fallback: second call asking Claude to re-format what it found
      if (!aiData) {
        const fallbackRes = await fetch("https://api.anthropic.com/v1/messages", {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body: JSON.stringify({
            model: "claude-sonnet-4-20250514",
            max_tokens: 1200,
            messages: [{
              role: "user",
              content: `La página del listado puede estar restringida. Con base en esta URL: ${url}
              
Extrae todo lo posible del slug de la URL (dirección, precio si aparece, etc.) y completa el resto con estimaciones reales del mercado de Miami.
Devuelve SOLO el JSON crudo sin backticks ni explicaciones:
{"address":"","neighborhood":"","city":"Miami","zipCode":"","propertyType":"Single Family","price":0,"beds":0,"baths":0,"sqft":0,"lotSize":0,"yearBuilt":0,"hoa":0,"taxes":0,"insurance":0,"zoningCode":"RS-1","folio":null,"currentUse":"Unknown","lastSalePrice":null,"lastSaleDate":null,"estimatedRent":0,"description":"","features":[],"daysOnMarket":0,"pricePerSqft":0,"listingAgent":"","mlsId":"","notes":"","_extractedFields":[],"_estimatedFields":["price","beds","baths","sqft","taxes","insurance","estimatedRent"],"_missingFields":[],"extractionNotes":"Página inaccesible. Valores basados en URL y estimaciones del mercado de Miami."}`
            }]
          }),
        });
        const fbData = await fallbackRes.json();
        const fbText = (fbData.content || []).filter(b => b.type === "text").map(b => b.text).join("").trim();
        const fbMatch = fbText.match(/\{[\s\S]*\}/);
        if (fbMatch) aiData = JSON.parse(fbMatch[0]);
      }

      if (!aiData) throw new Error("No se pudieron extraer datos de la propiedad.");

      const prop = buildPropertyFromAI(aiData, url, source);
      setProperty(prop);
      setLoadStep(2);
      await new Promise(r => setTimeout(r, 300));

      // ── PASO 2: Generar advisory estructurado en JSON para gráficas ──
      setLoadStep(3);
      const downPct = profile.downPayment || 20;
      const finBase = analyzeFinancials(prop, profile, "base");
      const finCons = analyzeFinancials(prop, profile, "conservative");
      const finAgr  = analyzeFinancials(prop, profile, "aggressive");
      const zoning  = analyzeZoning(prop);

      const advisoryPrompt = `Eres un asesor senior de bienes raíces en Miami. Analiza esta propiedad y devuelve un JSON estructurado para mostrar un dashboard de inversión en ESPAÑOL.

PROPIEDAD:
- Dirección: ${prop.address}, ${prop.neighborhood}, ${prop.city} ${prop.zipCode}
- Tipo: ${prop.propertyType} | Hab/Baños: ${prop.beds}/${prop.baths} | ${prop.livingArea} sqft | Terreno: ${prop.lotSize || "N/A"} sf
- Año construcción: ${prop.yearBuilt || "Desconocido"} | Zonificación: ${prop.zoningCode} | HOA: $${prop.hoa}/mes
- Precio: $${prop.price.toLocaleString()} | Precio/sqft: $${prop.price > 0 && prop.livingArea > 0 ? Math.round(prop.price/prop.livingArea) : "N/A"}
- Descripción del listado: ${aiData.description || "No disponible"}
- Características: ${(aiData.features || []).join(", ") || "No listadas"}
- Datos extraídos del listado: ${(prop._aiExtracted || []).join(", ") || "ninguno confirmado"}
- Datos estimados: ${(prop._aiEstimated || []).join(", ") || "ninguno"}

FINANCIEROS (escenario base, ${downPct}% enganche, tasa 7.25%, 30 años):
- Préstamo: $${finBase.loanAmount.toLocaleString()} | Hipoteca P&I: $${finBase.mortgagePI.toLocaleString()}/mes
- Impuestos: $${finBase.taxesMonthly.toLocaleString()}/mes | Seguro: $${finBase.insuranceMonthly.toLocaleString()}/mes | HOA: $${finBase.hoaMonthly}/mes
- Costo mensual total: $${finBase.totalMonthlyCost.toLocaleString()}
- Renta estimada: $${finBase.monthlyRent.toLocaleString()}/mes | Ingreso bruto anual: $${finBase.grossIncome.toLocaleString()}
- NOI: $${finBase.noi.toLocaleString()} | Flujo anual: $${finBase.annualCashFlow.toLocaleString()}
- Cap Rate: ${finBase.capRate}% | Cash-on-Cash: ${finBase.cashOnCash}% | Enganche: $${finBase.downPaymentAmt.toLocaleString()}

ESCENARIO CONSERVADOR: renta $${finCons.monthlyRent}/mes | NOI $${finCons.noi} | flujo $${finCons.annualCashFlow}
ESCENARIO AGRESIVO: renta $${finAgr.monthlyRent}/mes | NOI $${finAgr.noi} | flujo $${finAgr.annualCashFlow}

ZONIFICACIÓN: ${zoning.densityClue} | Unidades máx est: ${zoning.maxUnitsEstimated} | ADU: ${zoning.aduPotential} | Duplex: ${zoning.duplexPotential} | Multifamiliar: ${zoning.multifamilyPotential}

Devuelve SOLO este JSON (sin markdown, sin backticks):
{
  "scoreInversion": 0,
  "scoreDescripcion": "texto explicando el score",
  "veredicto": "COMPRAR | NEGOCIAR | EVITAR | ANALIZAR MÁS",
  "veredictoColor": "#16a34a | #d97706 | #dc2626 | #2563eb",
  "resumen": "2-3 oraciones describiendo la propiedad y su contexto en el mercado de Miami",
  "puntosPositivos": ["punto 1", "punto 2", "punto 3"],
  "puntosNegativos": ["riesgo 1", "riesgo 2", "riesgo 3"],
  "mejorUso": "Vivienda principal | Renta a largo plazo | Renta a corto plazo | House hacking | Desarrollo | Flip",
  "mejorUsoRazon": "explicación breve",
  "precioOferta": 0,
  "precioOfertaRazon": "por qué ese precio",
  "rentaRangoMin": 0,
  "rentaRangoMax": 0,
  "rentaRangoNota": "explicación del rango de renta",
  "breakEvenOcupacion": 0,
  "apreciacionAnual": 4.5,
  "riesgos": [
    {"titulo": "riesgo 1", "descripcion": "detalle", "nivel": "alto | medio | bajo"},
    {"titulo": "riesgo 2", "descripcion": "detalle", "nivel": "alto | medio | bajo"},
    {"titulo": "riesgo 3", "descripcion": "detalle", "nivel": "alto | medio | bajo"}
  ],
  "zonificacionNota": "análisis de zonificación y potencial de desarrollo",
  "proximosPasos": ["paso 1", "paso 2", "paso 3"],
  "comparativaMercado": {
    "precioMercado": 0,
    "precioListado": 0,
    "rentaMercado": 0,
    "rentaEstimada": 0,
    "capRateMercado": 0,
    "capRatePropiedad": 0
  },
  "proyeccionPatrimonio": [
    {"anio": 1, "valorPropiedad": 0, "balancePrestamo": 0, "patrimonio": 0},
    {"anio": 3, "valorPropiedad": 0, "balancePrestamo": 0, "patrimonio": 0},
    {"anio": 5, "valorPropiedad": 0, "balancePrestamo": 0, "patrimonio": 0},
    {"anio": 10, "valorPropiedad": 0, "balancePrestamo": 0, "patrimonio": 0}
  ]
}

Sé honesto y específico para el mercado de Miami. No exageres. Usa números reales.`;

      const advisoryRes = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 2000,
          messages: [{ role: "user", content: advisoryPrompt }],
        }),
      });
      const advisoryData = await advisoryRes.json();
      const advText = (advisoryData.content || []).filter(b => b.type === "text").map(b => b.text).join("").trim();
      const advMatch = advText.match(/\{[\s\S]*\}/);
      let advisory = null;
      if (advMatch) {
        try { advisory = JSON.parse(advMatch[0]); } catch {}
      }

      setAiReport(advisory);
      setPhase("result");

    } catch (err) {
      console.error(err);
      setErrorMsg("No se pudo analizar este link. Verificá la URL e intentá nuevamente.");
      setPhase("error");
    }
  };

  // Inline field editor
  const startEdit = () => {
    if (!property) return;
    setEditFields({
      price: property.price, beds: property.beds, baths: property.baths,
      sqft: property.livingArea, hoa: property.hoa, lotSize: property.lotSize,
      yearBuilt: property.yearBuilt, zoningCode: property.zoningCode,
      estimatedRent: property.estimatedRent,
    });
    setEditMode(true);
  };

  const applyEdits = () => {
    if (!property) return;
    const updated = {
      ...property,
      price: Number(editFields.price) || property.price,
      beds: Number(editFields.beds) || property.beds,
      baths: Number(editFields.baths) || property.baths,
      livingArea: Number(editFields.sqft) || property.livingArea,
      hoa: Number(editFields.hoa) || 0,
      lotSize: Number(editFields.lotSize) || property.lotSize,
      yearBuilt: Number(editFields.yearBuilt) || property.yearBuilt,
      zoningCode: editFields.zoningCode || property.zoningCode,
      estimatedRent: Number(editFields.estimatedRent) || property.estimatedRent,
      taxes: Math.round((Number(editFields.price) || property.price) * 0.011),
      insuranceEstimate: Math.round((Number(editFields.price) || property.price) * 0.005),
    };
    setProperty(updated);
    setEditMode(false);
  };

  // ── CHART HELPERS ──
  const BarChart = ({ data, height = 160, color = "#10b981", label }) => {
    const max = Math.max(...data.map(d => Math.abs(d.value)), 1);
    return (
      <div>
        {label && <div style={{ fontSize: 12, fontWeight: 600, color: "#6b7280", marginBottom: 8, textTransform: "uppercase", letterSpacing: "0.4px" }}>{label}</div>}
        <div style={{ display: "flex", alignItems: "flex-end", gap: 8, height }}>
          {data.map((d, i) => {
            const pct = Math.abs(d.value) / max;
            const isNeg = d.value < 0;
            return (
              <div key={i} style={{ flex: 1, display: "flex", flexDirection: "column", alignItems: "center", gap: 4 }}>
                <div style={{ fontSize: 11, fontWeight: 700, color: isNeg ? "#dc2626" : color }}>
                  {d.value >= 0 ? "+" : ""}${Math.abs(d.value).toLocaleString()}
                </div>
                <div style={{ width: "100%", height: Math.max(pct * (height - 40), 4), background: isNeg ? "#fee2e2" : color, borderRadius: "4px 4px 0 0", border: isNeg ? "1px solid #fca5a5" : "none" }} />
                <div style={{ fontSize: 11, color: "#6b7280", textAlign: "center", lineHeight: 1.2 }}>{d.label}</div>
              </div>
            );
          })}
        </div>
      </div>
    );
  };

  const DonutChart = ({ value, max = 100, size = 120, color = "#10b981", label, sub }) => {
    const pct = Math.min(value / max, 1);
    const r = 44;
    const circ = 2 * Math.PI * r;
    const dash = circ * pct;
    return (
      <div style={{ display: "flex", flexDirection: "column", alignItems: "center", gap: 4 }}>
        <svg width={size} height={size} viewBox="0 0 100 100">
          <circle cx="50" cy="50" r={r} fill="none" stroke="#f3f4f6" strokeWidth="10" />
          <circle cx="50" cy="50" r={r} fill="none" stroke={color} strokeWidth="10"
            strokeDasharray={`${dash} ${circ - dash}`} strokeDashoffset={circ * 0.25}
            strokeLinecap="round" style={{ transition: "stroke-dasharray 1s ease" }} />
          <text x="50" y="46" textAnchor="middle" fontSize="18" fontWeight="700" fill="#111827">{value}</text>
          <text x="50" y="60" textAnchor="middle" fontSize="9" fill="#6b7280">{sub || "/100"}</text>
        </svg>
        {label && <div style={{ fontSize: 12, fontWeight: 600, color: "#374151", textAlign: "center" }}>{label}</div>}
      </div>
    );
  };

  const HorizBar = ({ label, value, max, color = "#10b981", fmt: fmtFn }) => {
    const pct = Math.min(Math.abs(value) / max, 1) * 100;
    return (
      <div style={{ marginBottom: 10 }}>
        <div style={{ display: "flex", justifyContent: "space-between", marginBottom: 4, fontSize: 13 }}>
          <span style={{ color: "#374151" }}>{label}</span>
          <span style={{ fontWeight: 700, color: value < 0 ? "#dc2626" : "#111827" }}>{fmtFn ? fmtFn(value) : value}</span>
        </div>
        <div style={{ background: "#f3f4f6", borderRadius: 99, height: 8 }}>
          <div style={{ width: `${pct}%`, height: 8, background: value < 0 ? "#dc2626" : color, borderRadius: 99, transition: "width 0.8s ease" }} />
        </div>
      </div>
    );
  };

  const ScenarioToggle = ({ value, onChange }) => (
    <div style={{ display: "flex", background: "#f3f4f6", borderRadius: 10, padding: 3, gap: 2 }}>
      {[["conservative","Conservador"],["base","Base"],["aggressive","Optimista"]].map(([k, label]) => (
        <button key={k} onClick={() => onChange(k)}
          style={{ background: value === k ? "white" : "transparent", color: value === k ? "#111827" : "#6b7280", border: "none", borderRadius: 8, padding: "7px 14px", fontSize: 12, fontWeight: value === k ? 700 : 400, cursor: "pointer", boxShadow: value === k ? "0 1px 4px rgba(0,0,0,0.1)" : "none" }}>
          {label}
        </button>
      ))}
    </div>
  );

  const RiskBadge = ({ nivel }) => {
    const m = { alto: { bg: "#fee2e2", color: "#991b1b", label: "Alto" }, medio: { bg: "#fef3c7", color: "#92400e", label: "Medio" }, bajo: { bg: "#d1fae5", color: "#065f46", label: "Bajo" } };
    const s = m[nivel] || m.medio;
    return <span style={{ background: s.bg, color: s.color, fontSize: 11, fontWeight: 700, padding: "2px 8px", borderRadius: 99 }}>{s.label}</span>;
  };

  const renderDataBadges = (prop) => (
    <div style={{ display: "flex", flexWrap: "wrap", gap: 6 }}>
      {(prop._aiExtracted || []).map(f => <CPill key={f} label={f} type="extracted" />)}
      {(prop._aiEstimated || []).map(f => <CPill key={f} label={f} type="estimated" />)}
      {(prop._aiMissing   || []).map(f => <CPill key={f} label={f} type="missing" />)}
    </div>
  );

  return (
    <div style={{ minHeight: "100vh", background: "#f8fafc", fontFamily: "sans-serif" }}>
      <div style={{ background: "#0f172a", padding: "20px 32px", display: "flex", justifyContent: "space-between", alignItems: "center" }}>
        <button onClick={onBack} style={{ background: "transparent", color: "#94a3b8", border: "none", cursor: "pointer", fontSize: 14 }}>← Volver</button>
        <div style={{ fontSize: 13, color: "#10b981", letterSpacing: "0.5px" }}>ANÁLISIS DE PROPIEDAD</div>
        <div style={{ width: 80 }} />
      </div>

      <div style={{ maxWidth: 860, margin: "0 auto", padding: "32px 20px" }}>

        {/* ─── INPUT ─── */}
        {phase === "input" && (
          <div style={{ background: "white", borderRadius: 20, border: "1px solid #e5e7eb", padding: "44px 40px" }}>
            <div style={{ fontSize: 13, color: "#10b981", marginBottom: 14, letterSpacing: "0.5px" }}>ANÁLISIS INTELIGENTE CON IA</div>
            <h2 style={{ fontSize: 30, fontWeight: 700, marginBottom: 12, fontFamily: "Georgia, serif", color: "#0f172a", lineHeight: 1.2 }}>
              Pegá el link.<br />Nosotros hacemos el análisis.
            </h2>
            <p style={{ color: "#6b7280", fontSize: 16, lineHeight: 1.7, marginBottom: 32, maxWidth: 540 }}>
              Cualquier link de Zillow, Redfin, Realtor.com, LoopNet u otro portal. La IA lee el listado real, extrae todos los datos, corre el modelo financiero y entrega un reporte completo en español. Sin formularios.
            </p>
            <div style={{ display: "flex", gap: 12, marginBottom: 16 }}>
              <input value={url} onChange={e => setUrl(e.target.value)}
                onKeyDown={e => e.key === "Enter" && url.trim() && handleAnalyze()}
                placeholder="https://www.zillow.com/homedetails/..."
                style={{ flex: 1, background: "#f9fafb", border: "1.5px solid #d1d5db", borderRadius: 12, padding: "15px 18px", fontSize: 15, color: "#111827", fontFamily: "sans-serif" }} />
              <button onClick={handleAnalyze} disabled={!url.trim()}
                style={{ background: url.trim() ? "linear-gradient(135deg, #10b981, #059669)" : "#e5e7eb", color: url.trim() ? "white" : "#9ca3af", border: "none", borderRadius: 12, padding: "15px 28px", fontSize: 15, fontWeight: 700, cursor: url.trim() ? "pointer" : "not-allowed", whiteSpace: "nowrap" }}>
                Analizar →
              </button>
            </div>
            <div style={{ display: "flex", gap: 8, flexWrap: "wrap" }}>
              {["Zillow","Redfin","Realtor.com","LoopNet","Crexi","Cualquier URL"].map(s => (
                <span key={s} style={{ background: "#f3f4f6", color: "#6b7280", fontSize: 12, padding: "4px 10px", borderRadius: 99 }}>{s}</span>
              ))}
            </div>
          </div>
        )}

        {/* ─── LOADING ─── */}
        {phase === "loading" && (
          <div style={{ background: "white", borderRadius: 20, border: "1px solid #e5e7eb", padding: "48px 40px" }}>
            <div style={{ fontSize: 13, color: "#10b981", marginBottom: 14 }}>PROCESANDO</div>
            <h2 style={{ fontSize: 22, fontWeight: 700, marginBottom: 8, fontFamily: "Georgia, serif", color: "#0f172a" }}>Analizando tu propiedad…</h2>
            <div style={{ fontSize: 12, color: "#6b7280", marginBottom: 16, wordBreak: "break-all" }}>🔗 {url}</div>
            <LoadStep steps={["Leyendo el listado real", "Extrayendo datos con IA", "Calculando financieros", "Generando reporte de inversión"]} current={loadStep} />
            <div style={{ fontSize: 12, color: "#9ca3af", marginTop: 8 }}>Esto toma entre 20 y 40 segundos</div>
          </div>
        )}

        {/* ─── ERROR ─── */}
        {phase === "error" && (
          <div style={{ background: "white", borderRadius: 20, border: "1px solid #fee2e2", padding: "40px 36px", textAlign: "center" }}>
            <div style={{ fontSize: 32, marginBottom: 16 }}>⚠️</div>
            <h3 style={{ fontSize: 20, fontWeight: 700, color: "#991b1b", marginBottom: 12 }}>No se pudo analizar el link</h3>
            <p style={{ color: "#6b7280", marginBottom: 24 }}>{errorMsg}</p>
            <button onClick={() => setPhase("input")} style={{ background: "#0f172a", color: "white", border: "none", borderRadius: 10, padding: "12px 24px", fontSize: 14, fontWeight: 600, cursor: "pointer" }}>
              Intentar con otro link
            </button>
          </div>
        )}

        {/* ─── RESULTADO ─── */}
        {phase === "result" && property && (() => {
          const adv = aiReport || {};
          const fin = analyzeFinancials(property, profile, scenario);
          const finC = analyzeFinancials(property, profile, "conservative");
          const finA = analyzeFinancials(property, profile, "aggressive");
          const zoning = analyzeZoning(property);
          const proj = adv.proyeccionPatrimonio || [];

          return (
            <div>
              {/* URL + acciones */}
              <div style={{ background: "white", borderRadius: 12, border: "1px solid #e5e7eb", padding: "12px 16px", marginBottom: 16, display: "flex", justifyContent: "space-between", alignItems: "center", flexWrap: "wrap", gap: 8 }}>
                <div style={{ fontSize: 12, color: "#6b7280", wordBreak: "break-all", flex: 1 }}>🔗 {url}</div>
                <div style={{ display: "flex", gap: 8 }}>
                  <button onClick={startEdit} style={{ background: "#f3f4f6", color: "#374151", border: "none", borderRadius: 8, padding: "6px 12px", fontSize: 12, fontWeight: 600, cursor: "pointer" }}>Editar datos</button>
                  <button onClick={() => setPhase("input")} style={{ background: "#f3f4f6", color: "#374151", border: "none", borderRadius: 8, padding: "6px 12px", fontSize: 12, fontWeight: 600, cursor: "pointer" }}>Nuevo link</button>
                </div>
              </div>

              {/* Confianza de datos */}
              <div style={{ background: "white", borderRadius: 14, border: "1px solid #e5e7eb", padding: "14px 20px", marginBottom: 16 }}>
                <div style={{ fontSize: 12, fontWeight: 700, color: "#374151", marginBottom: 8 }}>CONFIANZA DE DATOS</div>
                {renderDataBadges(property)}
                {property._extractionNotes && <div style={{ fontSize: 12, color: "#6b7280", marginTop: 8, fontStyle: "italic" }}>{property._extractionNotes}</div>}
              </div>

              {/* Editor inline */}
              {editMode && (
                <div style={{ background: "#fffbeb", border: "1px solid #fde68a", borderRadius: 14, padding: "20px 24px", marginBottom: 16 }}>
                  <div style={{ fontSize: 14, fontWeight: 700, color: "#92400e", marginBottom: 14 }}>Editar valores extraídos</div>
                  <div style={{ display: "grid", gridTemplateColumns: "repeat(3, 1fr)", gap: 10, marginBottom: 14 }}>
                    {[["price","Precio ($)"],["beds","Habitaciones"],["baths","Baños"],["sqft","Sup. (sqft)"],["hoa","HOA/mes ($)"],["lotSize","Terreno (sqft)"],["yearBuilt","Año construcción"],["zoningCode","Zonificación"],["estimatedRent","Renta mensual ($)"]].map(([k, lbl]) => (
                      <div key={k}>
                        <label style={{ fontSize: 11, color: "#6b7280", display: "block", marginBottom: 3 }}>{lbl}</label>
                        <input value={editFields[k] || ""} onChange={e => setEditFields(p => ({ ...p, [k]: e.target.value }))}
                          style={{ width: "100%", background: "white", border: "1px solid #fde68a", borderRadius: 6, padding: "8px 10px", fontSize: 13, boxSizing: "border-box", fontFamily: "sans-serif" }} />
                      </div>
                    ))}
                  </div>
                  <div style={{ display: "flex", gap: 8 }}>
                    <button onClick={applyEdits} style={{ background: "#10b981", color: "white", border: "none", borderRadius: 8, padding: "10px 20px", fontSize: 13, fontWeight: 600, cursor: "pointer" }}>Aplicar cambios</button>
                    <button onClick={() => setEditMode(false)} style={{ background: "#f3f4f6", color: "#374151", border: "none", borderRadius: 8, padding: "10px 20px", fontSize: 13, fontWeight: 600, cursor: "pointer" }}>Cancelar</button>
                  </div>
                </div>
              )}

              {/* ── HERO + VEREDICTO ── */}
              <div style={{ display: "grid", gridTemplateColumns: "1fr auto", gap: 16, marginBottom: 16, alignItems: "stretch" }}>
                <div style={{ background: "linear-gradient(135deg, #1a4a6bdd, #1a4a6b55)", borderRadius: 18, padding: "24px 28px", color: "white" }}>
                  <div style={{ fontSize: 12, opacity: 0.65, marginBottom: 4 }}>{property.propertyType} · {property.zoningCode}</div>
                  <h2 style={{ fontSize: 20, fontWeight: 700, marginBottom: 4, fontFamily: "Georgia, serif" }}>{property.address}</h2>
                  <div style={{ fontSize: 13, opacity: 0.75, marginBottom: 20 }}>{property.neighborhood}{property.zipCode ? ` · ${property.zipCode}` : ""}</div>
                  <div style={{ display: "flex", gap: 24, flexWrap: "wrap" }}>
                    {[
                      { v: `$${property.price.toLocaleString()}`, l: "Precio" },
                      property.beds > 0 && { v: `${property.beds}/${property.baths}`, l: "Hab/Baños" },
                      property.livingArea > 0 && { v: `${property.livingArea.toLocaleString()} sf`, l: "Superficie" },
                      property.yearBuilt > 0 && { v: property.yearBuilt, l: "Año" },
                      property.hoa > 0 && { v: `$${property.hoa}/mes`, l: "HOA" },
                    ].filter(Boolean).map(item => (
                      <div key={item.l}>
                        <div style={{ fontSize: 18, fontWeight: 800 }}>{item.v}</div>
                        <div style={{ fontSize: 10, opacity: 0.6 }}>{item.l}</div>
                      </div>
                    ))}
                  </div>
                  {adv.resumen && <div style={{ fontSize: 13, opacity: 0.85, marginTop: 16, lineHeight: 1.6, borderTop: "1px solid rgba(255,255,255,0.15)", paddingTop: 14 }}>{adv.resumen}</div>}
                </div>

                {/* Score + Veredicto */}
                <div style={{ background: "white", border: "1px solid #e5e7eb", borderRadius: 18, padding: "20px 24px", display: "flex", flexDirection: "column", alignItems: "center", justifyContent: "center", minWidth: 180, gap: 12 }}>
                  <DonutChart value={adv.scoreInversion || 0} size={110} color={adv.veredictoColor || "#10b981"} label="Score de inversión" sub="/100" />
                  {adv.veredicto && (
                    <div style={{ background: adv.veredictoColor || "#10b981", color: "white", fontSize: 13, fontWeight: 800, padding: "8px 16px", borderRadius: 10, textAlign: "center", letterSpacing: "0.5px" }}>
                      {adv.veredicto}
                    </div>
                  )}
                  {adv.mejorUso && (
                    <div style={{ fontSize: 12, color: "#6b7280", textAlign: "center", lineHeight: 1.4 }}>
                      <span style={{ fontWeight: 600, color: "#374151" }}>Mejor uso:</span><br />{adv.mejorUso}
                    </div>
                  )}
                </div>
              </div>

              {/* ── PROS / CONTRAS ── */}
              {(adv.puntosPositivos || adv.puntosNegativos) && (
                <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 12, marginBottom: 16 }}>
                  <div style={{ background: "#f0fdf4", border: "1px solid #bbf7d0", borderRadius: 14, padding: "18px 20px" }}>
                    <div style={{ fontSize: 12, fontWeight: 700, color: "#166534", marginBottom: 12, textTransform: "uppercase", letterSpacing: "0.4px" }}>✓ Puntos positivos</div>
                    {(adv.puntosPositivos || []).map((p, i) => (
                      <div key={i} style={{ fontSize: 13, color: "#166534", marginBottom: 8, display: "flex", gap: 8 }}>
                        <span style={{ flexShrink: 0 }}>▸</span><span>{p}</span>
                      </div>
                    ))}
                  </div>
                  <div style={{ background: "#fff7ed", border: "1px solid #fed7aa", borderRadius: 14, padding: "18px 20px" }}>
                    <div style={{ fontSize: 12, fontWeight: 700, color: "#9a3412", marginBottom: 12, textTransform: "uppercase", letterSpacing: "0.4px" }}>⚠ Riesgos</div>
                    {(adv.riesgos || []).map((r, i) => (
                      <div key={i} style={{ marginBottom: 10 }}>
                        <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 2 }}>
                          <div style={{ fontSize: 13, fontWeight: 600, color: "#9a3412" }}>{r.titulo}</div>
                          <RiskBadge nivel={r.nivel} />
                        </div>
                        <div style={{ fontSize: 12, color: "#78350f", lineHeight: 1.5 }}>{r.descripcion}</div>
                      </div>
                    ))}
                  </div>
                </div>
              )}

              {/* ── ANÁLISIS FINANCIERO VISUAL ── */}
              <div style={{ background: "white", borderRadius: 16, border: "1px solid #e5e7eb", padding: "22px 24px", marginBottom: 16 }}>
                <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 20 }}>
                  <h3 style={{ fontSize: 16, fontWeight: 700, margin: 0 }}>Análisis Financiero</h3>
                  <ScenarioToggle value={scenario} onChange={setScenario} />
                </div>

                {/* KPIs top */}
                <div style={{ display: "grid", gridTemplateColumns: "repeat(4, 1fr)", gap: 10, marginBottom: 20 }}>
                  {[
                    { l: "Costo mensual total", v: `$${fin.totalMonthlyCost.toLocaleString()}`, hi: false },
                    { l: "NOI anual", v: fin.noi > 0 ? `$${fin.noi.toLocaleString()}` : `-$${Math.abs(fin.noi).toLocaleString()}`, hi: fin.noi > 0 },
                    { l: "Cap Rate", v: fin.capRate !== "N/A" ? `${fin.capRate}%` : "N/A", hi: parseFloat(fin.capRate) > 4 },
                    { l: "Cash-on-Cash", v: fin.cashOnCash !== "N/A" ? `${fin.cashOnCash}%` : "N/A", hi: parseFloat(fin.cashOnCash) > 5 },
                  ].map(k => (
                    <div key={k.l} style={{ background: k.hi ? "#f0fdf4" : "#f9fafb", border: k.hi ? "1px solid #bbf7d0" : "1px solid #e5e7eb", borderRadius: 10, padding: "12px 14px" }}>
                      <div style={{ fontSize: 11, color: "#6b7280", marginBottom: 4, textTransform: "uppercase", letterSpacing: "0.4px" }}>{k.l}</div>
                      <div style={{ fontSize: 20, fontWeight: 800, color: k.hi ? "#15803d" : "#111827" }}>{k.v}</div>
                    </div>
                  ))}
                </div>

                {/* Desglose de costos — gráfica horizontal */}
                <div style={{ marginBottom: 20 }}>
                  <div style={{ fontSize: 12, fontWeight: 600, color: "#6b7280", marginBottom: 12, textTransform: "uppercase", letterSpacing: "0.4px" }}>Desglose de costos mensuales</div>
                  {[
                    { label: "Hipoteca P&I", value: fin.mortgagePI, color: "#3b82f6" },
                    { label: "Impuestos", value: fin.taxesMonthly, color: "#8b5cf6" },
                    { label: "Seguro", value: fin.insuranceMonthly, color: "#f59e0b" },
                    { label: "HOA", value: fin.hoaMonthly, color: "#ec4899" },
                    { label: "Reservas", value: fin.maintenanceReserve, color: "#6b7280" },
                  ].filter(d => d.value > 0).map(d => (
                    <HorizBar key={d.label} label={d.label} value={d.value} max={fin.totalMonthlyCost} color={d.color} fmtFn={v => `$${v.toLocaleString()}/mes`} />
                  ))}
                </div>

                {/* Flujo de caja por escenario — barras verticales */}
                {property.estimatedRent > 0 && (
                  <div style={{ marginBottom: 8 }}>
                    <BarChart label="Flujo de caja anual por escenario" height={180} color="#10b981"
                      data={[
                        { label: "Conservador", value: finC.annualCashFlow },
                        { label: "Base", value: fin.annualCashFlow },
                        { label: "Optimista", value: finA.annualCashFlow },
                      ]} />
                    <div style={{ display: "grid", gridTemplateColumns: "repeat(3, 1fr)", gap: 10, marginTop: 12 }}>
                      {[
                        { lbl: "Conservador", f: finC },
                        { lbl: "Base", f: fin },
                        { lbl: "Optimista", f: finA },
                      ].map(({ lbl, f }) => (
                        <div key={lbl} style={{ background: "#f9fafb", borderRadius: 8, padding: "10px 12px", textAlign: "center" }}>
                          <div style={{ fontSize: 11, color: "#6b7280", marginBottom: 4 }}>{lbl}</div>
                          <div style={{ fontSize: 13, fontWeight: 700, color: "#374151" }}>Renta: ${f.monthlyRent.toLocaleString()}/mes</div>
                          <div style={{ fontSize: 12, color: f.annualCashFlow >= 0 ? "#16a34a" : "#dc2626" }}>
                            Flujo: {f.annualCashFlow >= 0 ? "+" : ""}${f.annualCashFlow.toLocaleString()}/año
                          </div>
                          <div style={{ fontSize: 11, color: "#9ca3af" }}>Cap: {f.capRate}% · CoC: {f.cashOnCash}%</div>
                        </div>
                      ))}
                    </div>
                  </div>
                )}

                {/* Renta estimada */}
                {adv.rentaRangoMin && (
                  <div style={{ background: "#eff6ff", border: "1px solid #bfdbfe", borderRadius: 10, padding: "12px 16px", marginTop: 12 }}>
                    <div style={{ fontSize: 12, fontWeight: 700, color: "#1e40af", marginBottom: 4 }}>Rango de renta de mercado</div>
                    <div style={{ fontSize: 18, fontWeight: 800, color: "#1d4ed8" }}>
                      ${(adv.rentaRangoMin || 0).toLocaleString()} – ${(adv.rentaRangoMax || 0).toLocaleString()}/mes
                    </div>
                    {adv.rentaRangoNota && <div style={{ fontSize: 12, color: "#3b82f6", marginTop: 4 }}>{adv.rentaRangoNota}</div>}
                  </div>
                )}

                <div style={{ fontSize: 11, color: "#9ca3af", fontStyle: "italic", marginTop: 12 }}>
                  * Tasa 7.25%, {profile.downPayment || 20}% enganche, 30 años, 8% vacancia, 10% administración, 1% mantenimiento anual.
                </div>
              </div>

              {/* ── PROYECCIÓN DE PATRIMONIO ── */}
              {proj.length > 0 && (
                <div style={{ background: "white", borderRadius: 16, border: "1px solid #e5e7eb", padding: "22px 24px", marginBottom: 16 }}>
                  <h3 style={{ fontSize: 16, fontWeight: 700, marginBottom: 16 }}>Proyección de Patrimonio</h3>
                  <div style={{ display: "flex", alignItems: "flex-end", gap: 16 }}>
                    {proj.map(p => {
                      const maxP = Math.max(...proj.map(x => x.patrimonio), 1);
                      const pct = p.patrimonio / maxP;
                      return (
                        <div key={p.anio} style={{ flex: 1, display: "flex", flexDirection: "column", alignItems: "center", gap: 6 }}>
                          <div style={{ fontSize: 12, fontWeight: 700, color: "#16a34a" }}>${Math.round(p.patrimonio / 1000)}K</div>
                          <div style={{ width: "100%", height: Math.max(pct * 140, 8), background: "linear-gradient(to top, #10b981, #34d399)", borderRadius: "4px 4px 0 0" }} />
                          <div style={{ fontSize: 11, color: "#6b7280" }}>Año {p.anio}</div>
                          <div style={{ fontSize: 10, color: "#9ca3af" }}>Val: ${Math.round((p.valorPropiedad || 0) / 1000)}K</div>
                        </div>
                      );
                    })}
                  </div>
                  <div style={{ fontSize: 11, color: "#9ca3af", marginTop: 12, fontStyle: "italic" }}>
                    * Asume apreciación anual de {adv.apreciacionAnual || 4.5}% (promedio histórico Miami). Patrimonio = valor propiedad − saldo hipoteca.
                  </div>
                </div>
              )}

              {/* ── COMPARATIVA DE MERCADO ── */}
              {adv.comparativaMercado && (
                <div style={{ background: "white", borderRadius: 16, border: "1px solid #e5e7eb", padding: "22px 24px", marginBottom: 16 }}>
                  <h3 style={{ fontSize: 16, fontWeight: 700, marginBottom: 16 }}>Comparativa con el Mercado</h3>
                  <div style={{ display: "grid", gridTemplateColumns: "repeat(3, 1fr)", gap: 12 }}>
                    {[
                      { label: "Precio", listing: adv.comparativaMercado.precioListado, market: adv.comparativaMercado.precioMercado, fmt: v => `$${(v||0).toLocaleString()}`, lowerIsBetter: true },
                      { label: "Renta est.", listing: adv.comparativaMercado.rentaEstimada, market: adv.comparativaMercado.rentaMercado, fmt: v => `$${(v||0).toLocaleString()}/mo`, lowerIsBetter: false },
                      { label: "Cap Rate", listing: adv.comparativaMercado.capRatePropiedad, market: adv.comparativaMercado.capRateMercado, fmt: v => `${(v||0).toFixed(1)}%`, lowerIsBetter: false },
                    ].map(c => {
                      const isGood = c.lowerIsBetter ? (c.listing <= c.market) : (c.listing >= c.market);
                      return (
                        <div key={c.label} style={{ background: "#f9fafb", borderRadius: 10, padding: "14px" }}>
                          <div style={{ fontSize: 11, fontWeight: 600, color: "#6b7280", marginBottom: 10, textTransform: "uppercase" }}>{c.label}</div>
                          <div style={{ display: "flex", justifyContent: "space-between", marginBottom: 6 }}>
                            <div><div style={{ fontSize: 10, color: "#9ca3af" }}>Esta prop.</div><div style={{ fontSize: 16, fontWeight: 700, color: isGood ? "#16a34a" : "#dc2626" }}>{c.fmt(c.listing)}</div></div>
                            <div style={{ textAlign: "right" }}><div style={{ fontSize: 10, color: "#9ca3af" }}>Mercado</div><div style={{ fontSize: 16, fontWeight: 700, color: "#374151" }}>{c.fmt(c.market)}</div></div>
                          </div>
                          <div style={{ fontSize: 11, color: isGood ? "#16a34a" : "#dc2626", fontWeight: 600 }}>
                            {isGood ? "✓ Favorable" : "▲ Desfavorable"}
                          </div>
                        </div>
                      );
                    })}
                  </div>
                </div>
              )}

              {/* ── ZONIFICACIÓN ── */}
              <div style={{ background: "white", borderRadius: 16, border: "1px solid #e5e7eb", padding: "22px 24px", marginBottom: 16 }}>
                <h3 style={{ fontSize: 16, fontWeight: 700, marginBottom: 14 }}>Zonificación y Potencial de Desarrollo</h3>
                <div style={{ display: "grid", gridTemplateColumns: "repeat(5, 1fr)", gap: 10, marginBottom: 14 }}>
                  {[
                    { l: "Código", v: zoning.zoningCode },
                    { l: "Unidades máx", v: zoning.maxUnitsEstimated, hi: zoning.maxUnitsEstimated > 1 },
                    { l: "ADU", v: zoning.aduPotential ? "Posible" : "Improbable", hi: zoning.aduPotential },
                    { l: "Duplex", v: zoning.duplexPotential ? "Posible" : "Improbable", hi: zoning.duplexPotential },
                    { l: "Multifam.", v: zoning.multifamilyPotential ? "Posible" : "Improbable", hi: zoning.multifamilyPotential },
                  ].map(k => (
                    <div key={k.l} style={{ background: k.hi ? "#f0fdf4" : "#f9fafb", border: k.hi ? "1px solid #bbf7d0" : "1px solid #e5e7eb", borderRadius: 10, padding: "10px 12px", textAlign: "center" }}>
                      <div style={{ fontSize: 10, color: "#6b7280", marginBottom: 3, textTransform: "uppercase" }}>{k.l}</div>
                      <div style={{ fontSize: 14, fontWeight: 700, color: k.hi ? "#15803d" : "#111827" }}>{k.v}</div>
                    </div>
                  ))}
                </div>
                {adv.zonificacionNota && <div style={{ fontSize: 13, color: "#4b5563", background: "#f8fafc", borderRadius: 10, padding: "12px 14px", lineHeight: 1.7 }}>{adv.zonificacionNota}</div>}
                <div style={{ fontSize: 11, color: "#9ca3af", marginTop: 8 }}>Verificar con City of Miami, Miami-Dade Property Search y Gridics Zoning Map.</div>
              </div>

              {/* ── PRECIO SUGERIDO + PRÓXIMOS PASOS ── */}
              <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 16, marginBottom: 16 }}>
                {adv.precioOferta > 0 && (
                  <div style={{ background: "linear-gradient(135deg, #eff6ff, #dbeafe)", border: "1px solid #bfdbfe", borderRadius: 16, padding: "20px 22px" }}>
                    <div style={{ fontSize: 12, fontWeight: 700, color: "#1e40af", marginBottom: 8, textTransform: "uppercase" }}>Precio de oferta sugerido</div>
                    <div style={{ fontSize: 28, fontWeight: 800, color: "#1d4ed8", marginBottom: 8 }}>${(adv.precioOferta || 0).toLocaleString()}</div>
                    {adv.precioOfertaRazon && <div style={{ fontSize: 13, color: "#2563eb", lineHeight: 1.6 }}>{adv.precioOfertaRazon}</div>}
                  </div>
                )}
                {adv.proximosPasos && (
                  <div style={{ background: "#f9fafb", border: "1px solid #e5e7eb", borderRadius: 16, padding: "20px 22px" }}>
                    <div style={{ fontSize: 12, fontWeight: 700, color: "#374151", marginBottom: 12, textTransform: "uppercase" }}>Próximos pasos</div>
                    {adv.proximosPasos.map((p, i) => (
                      <div key={i} style={{ display: "flex", gap: 10, marginBottom: 8, alignItems: "flex-start" }}>
                        <div style={{ width: 20, height: 20, borderRadius: "50%", background: "#0f172a", color: "white", fontSize: 11, fontWeight: 700, display: "flex", alignItems: "center", justifyContent: "center", flexShrink: 0 }}>{i+1}</div>
                        <div style={{ fontSize: 13, color: "#4b5563", lineHeight: 1.5 }}>{p}</div>
                      </div>
                    ))}
                  </div>
                )}
              </div>

              {/* ── SIMULADOR DE CASH FLOW ── */}
              <SimuladorCashFlow property={property} profile={profile} zoningInfo={zoning} />

              {/* ── CTA ── */}
              <div style={{ background: "linear-gradient(135deg, #0f172a, #1e293b)", borderRadius: 20, padding: "32px 28px", textAlign: "center", marginBottom: 16 }}>
                <div style={{ fontSize: 13, color: "#10b981", marginBottom: 10 }}>¿QUERÉS AVANZAR?</div>
                <h3 style={{ fontSize: 22, fontWeight: 700, color: "white", marginBottom: 10, fontFamily: "Georgia, serif" }}>Hablá con un asesor de Miami</h3>
                <p style={{ color: "#94a3b8", fontSize: 14, marginBottom: 20, maxWidth: 440, margin: "0 auto 20px" }}>Nuestro equipo puede verificar zonificación, correr comps reales, estructurar el financiamiento y negociar en tu nombre.</p>
                <button onClick={onLead} style={{ background: "linear-gradient(135deg, #10b981, #059669)", color: "white", border: "none", borderRadius: 12, padding: "14px 32px", fontSize: 15, fontWeight: 700, cursor: "pointer" }}>
                  Conectar con un asesor →
                </button>
              </div>

              {/* Disclaimer */}
              <div style={{ background: "#fffbeb", border: "1px solid #fde68a", borderRadius: 12, padding: "12px 16px", fontSize: 11, color: "#78350f", lineHeight: 1.7 }}>
                <strong>Aviso:</strong> Los datos fueron extraídos por IA del listado público disponible y pueden ser incompletos. Las proyecciones financieras son estimaciones con supuestos estándar del mercado de Miami-Dade. Este análisis no constituye asesoramiento financiero, legal ni inmobiliario. Siempre verificá los datos con el agente y consultá un profesional licenciado antes de hacer una oferta.
              </div>
            </div>
          );
        })()}
      </div>
    </div>
  );
};

// ============================================================
// MAIN APP
// ============================================================
export default function App() {
  const [page, setPage] = useState("landing");
  const [profile, setProfile] = useState({});
  const [selectedProperty, setSelectedProperty] = useState(null);
  const [compareProperties, setCompareProperties] = useState([]);

  return (
    <div>
      {page === "landing" && (
        <LandingPage
          onStart={() => setPage("intake")}
          onAnalyze={() => setPage("linkanalyzer")}
          onZoning={() => setPage("intake")}
        />
      )}
      {page === "intake" && (
        <IntakePage onComplete={(p) => { setProfile(p); setPage("results"); }} />
      )}
      {page === "linkanalyzer" && (
        <LinkAnalyzerPage
          profile={profile}
          onBack={() => setPage("landing")}
          onFullDetail={(p) => { setSelectedProperty(p); setPage("detail"); }}
          onLead={() => setPage("lead")}
        />
      )}
      {page === "results" && (
        <ResultsPage
          profile={profile}
          onSelect={(p) => { setSelectedProperty(p); setPage("detail"); }}
          onCompare={(props) => { setCompareProperties(props); setPage("compare"); }}
        />
      )}
      {page === "detail" && selectedProperty && (
        <DetailPage
          property={selectedProperty}
          profile={profile}
          onBack={() => setPage("results")}
          onLead={() => setPage("lead")}
        />
      )}
      {page === "compare" && (
        <ComparePage
          properties={compareProperties}
          profile={profile}
          onBack={() => setPage("results")}
        />
      )}
      {page === "lead" && (
        <LeadPage
          property={selectedProperty}
          profile={profile}
          onBack={() => setPage(selectedProperty ? "detail" : "results")}
        />
      )}
    </div>
  );
}
