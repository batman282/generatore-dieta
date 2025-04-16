# generatore-dieta
+document.getElementById('height').value;
            const weight = +document.getElementById('weight').value;
            const activity = +document.getElementById('activity').value;
            const goal = document.getElementById('goal').value;
            let bmr = gender === 'male' ?
              10 * weight + 6.25 * height - 5 * age + 5 :
              10 * weight + 6.25 * height - 5 * age - 161;
            let tdee = bmr * activity;
            if (goal === 'cut') tdee -= 300;
            if (goal === 'bulk') tdee += 300;
            const output = document.getElementById('output');
            output.innerHTML = `<h2>Fabbisogno Calorico: ${Math.round(tdee)} kcal</h2>`;
            for (let i = 1; i <= 7; i++) {
              let dayHTML = `<div class="day-plan"><h3>Giorno ${i}</h3>`;
              foods.forEach(f => {
                dayHTML += `<strong>${f.meal}:</strong><ul>`;
                f.items.forEach(item => dayHTML += `<li>${item}</li>`);
                dayHTML += '</ul>';
              });
              dayHTML += '</div>';
              output.innerHTML += dayHTML;
            }
          });
  </script>
</body>

</html>
