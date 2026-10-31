# Final PBIR queryRef conflict hotfix

Power BI Desktop error: `This queryRef 'FactBacktest.ME Trades' can only have one displayName.`

Cause: `02_Sector/visuals/risk_reward_bubble/visual.json` assigned both `Reported outcomes` and `Sample size (n)` as display names to the same `FactBacktest.ME Trades` queryRef (Size and Tooltips roles).

Fix: removed conflicting display-name overrides on those two appearances and made their native query references consistent with the measure name. Power BI will use the measure's normal name for this item; all other chart titles and data stay unchanged.

Verification: checked all PBIR visual projection references for contradictory display names; scanned 4 pages; original model.bim SHA256 identical; ZIP CRC verified.

**Power BI Desktop render not tested in this environment**. If further validation warnings occur, capture the precise error. The user's V4 Polished project remains separate and was already observed working.
