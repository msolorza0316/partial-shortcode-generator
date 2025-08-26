document.addEventListener("DOMContentLoaded", function() {
    function generatePartial() {
        const question = document.getElementById("question").value.trim();
        const labels = document.querySelectorAll("[data-label]");
        const values = document.querySelectorAll("[data-value]");
        let configArray = [];

        labels.forEach((label, index) => {
            const value = values[index].value.trim();
            if (label.value.trim() && value) {
                const escapedLabel = label.value.trim().replace(/"/g, '\\"');
                const escapedValue = value.replace(/"/g, '\\"');
                configArray.push(`{"label":"${escapedLabel}","value":"${escapedValue}"}`);
            }
        });

        let partialCode =
            `[partial id="finder-poll" question="${question.replace(/"/g, '\\"')}" config='${configArray.join(",")}']`;

        const output = document.getElementById("output");
        output.textContent = partialCode;
        output.style.display = "block";
    }

    document.getElementById("generate-partial-btn")
        .addEventListener("click", generatePartial);
});
