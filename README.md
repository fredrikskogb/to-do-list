// Works on PC. Needs to be edited on line 190-203 on MAC to work, doesn't grab inner.HTML.

if (dragSrcEl != this) {
            // Set the source column's HTML to the HTML of the column we dropped on.
            dragSrcEl.innerHTML = this.innerHTML;
            this.innerHTML = e.dataTransfer.getData('text/html');

            // Update the list in local storage after item is dropped
            let mainDiv = document.getElementById('listToDo');
            let newList = []; 
            for(let i = 0; i < mainDiv.children.length; i++){
                let x = mainDiv.children[i].children[0].innerHTML;
                newList.push(x);
            }
            localStorage.setItem("toDo", JSON.stringify(newList)); 
        }

https://fredrikskogb.github.io/to-do-list/
