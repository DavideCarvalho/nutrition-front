<script>
	let patientListPromise = getPatientList();

	async function getPatientList() {
	  const response = await fetch("http://localhost:8080/api/v1/pacient");
	  return await response.json();
	}
</script>

<h1>To aqui na tela de pacientes</h1>

<div>

{#await patientListPromise}

    <p>Loading patients</p>

    {:then patientList}

        {#each patientList as patient (patient.id)}
            <p>{patient.name}</p>
        {/each}

    {:catch error}

        <p style="color: red">{error}</p>

{/await}
</div>
