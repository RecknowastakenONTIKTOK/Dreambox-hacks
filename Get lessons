async function getName() {
    const response = await fetch('https://api.Dreambox.com/api/users/verify-lessons', {
        method: "GET",
        headers: {
            "accept": "application/json, text/plain, */*",
            "accept-language": "en-US,en;q=0.9,ru;q=0.8",
        },
        credentials: "include"
    });
    const data = await response.json();

    return data.name;
};

async function addCurrencies() {
    const Lessons = Number(prompt('How many Lessons do you want to add to your account? (5 daily)'));

    if (Lessons > 5) {
        alert('You can only add up to 5 Lessons daily.');
    };

    const response = await fetch('https://api.dreambox.com/api/users/add-rewards', {
        method: "PUT",
        headers: {
            "referer": "https://www.play.dreambox.com",
            "content-type": "application/json",
        },
        credentials: "include",
        body: JSON.stringify({
            addedlessons: lessons,
            addedXp: 30000,
            name: await getName()
        })
    });

    if (response.status == 200) {
        alert(`${lessons} lessons`);
    } else {
        alert('An error occured.');
    };

};

addCurrencies();
